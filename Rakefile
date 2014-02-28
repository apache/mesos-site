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
  FileUtils.mkdir_p(tmp_dir)
  system("git clone --depth 1 http://git-wip-us.apache.org/repos/asf/mesos.git #{tmp_dir}/mesos")
  puts "Updating docs to the latest version"
  FileUtils.rm_f(Dir.glob("source/documentation/latest/*.md"))
  FileUtils.cp_r(Dir.glob("#{tmp_dir}/mesos/docs/*.md"), File.expand_path("source/documentation/latest/"))
  puts "Parse documentation files to removing md extension in any links"
  Dir.chdir("#{docs_dir}/latest/") {
    Dir.glob('*.md').each { |doc|
      puts "working on: #{doc}"
      IO.write(doc, File.open(doc) { |f|
        f.read.gsub(/\((.*)(\.md)\)/, '(/documentation/latest/\1/)')
      })
    }
  }
  puts "Moving documentation index to its own 'latest' directory"
  FileUtils.mv("source/documentation/latest/home.md", "source/documentation/latest.html.md")
  puts "Documentation updated"
end

desc "Run the site in development mode. Preview available at http://localhost:4567/"
task :dev do
  system("middleman server")
end