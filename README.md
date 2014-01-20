# Apache Mesos website generator
This will generate the site available at http://mesos.apache.org. The content
within the publish folder will be the actual deployed site.


## Setup

		gem install bundler
		bundle install
		

## Generating the site
To generate the site one only needs to run `rake` after performing the setup
tasks mentioned above. This will download the latest Apache Mesos documentation
and integrate it into the site and generate all other files within the sources
folder.

		rake


## Developement 
To live edit the site run `rake dev` and then open a browser window to 
http://localhost:4567/ . Any change you make to the sources dir will 
be shown on the local dev site immediately. Errors will be shown in the 
console you launched `rake dev` within.


## Other available tasks

		rake build        # Build the website from source
		rake clean        # Remove any temporary products
		rake clobber      # Remove any generated file
		rake dev          # Run the site in development mode
		rake update_docs  # Update the latest docs from the Apache Mesos codebase

