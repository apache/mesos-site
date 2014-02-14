require 'rubygems'
require 'rake/clean'
require 'fileutils'

task :default => [:update_docs, :build, :clean]
 
CLEAN.include "tmp", "**/.DS_Store"

desc "Build the website from source"
task :build do
  puts "Building website from static source"
  result = system("middleman build --clean")
  if result 
    puts "Successfully generated the site, please commit your changes"
  else
    puts "An error was encountered when generating the site"
  end
end

desc "Update the latest docs from the Apache Mesos codebase"
task :update_docs do
  puts "Updating latest documentation from the Apache Mesos codebase" 
  
  tmp_dir = File.join(File.dirname(__FILE__), "tmp")
  docs_dir = File.join(File.dirname(__FILE__), "source/documentation")
  Rake::Task[:clean].invoke if File.exist?(tmp_dir)
  
  puts "Cloning Apache Mesos codebase"
  system("mkdir -p #{tmp_dir}")
  system("git clone --depth 1 http://git-wip-us.apache.org/repos/asf/mesos.git #{tmp_dir}/mesos")
  puts "Updating docs to the latest version"
  system("rm -f source/documentation/latest/*.md")
  system("cp -a #{tmp_dir}/mesos/docs/*.md source/documentation/latest/")
  puts "Parse documentation files, removing md extension and making links relative"
  # loop through directory of files, passing filenames
  Dir.foreach("#{docs_dir}/latest/") do |doc|
    next if doc == "." or doc == ".."
    # do work on real documents
    puts "working on: #{doc}"
    # find links, removing .md extensions from urls
    system("sed 's/.md//g' #{docs_dir}/latest/#{doc} > #{docs_dir}/latest/#{doc}.temp")
    system("mv #{docs_dir}/latest/#{doc}.temp #{docs_dir}/latest/#{doc}")
  end
  puts "Moving documentation index to its own 'latest' directory"
  system("mv source/documentation/latest/home.md source/documentation/latest.md")
  puts "Documentation updated"
end
 
desc "Run the site in development mode. Preview available at http://localhost:4567/"
task :dev do
  system("middleman server")
end