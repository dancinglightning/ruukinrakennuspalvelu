#!/usr/bin/env rake
# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require File.expand_path('../config/application', __FILE__)

Rrlvip::Application.load_tasks


desc "Create the static content for upload to server. (to ./ruukinrakennuspalvelu.fi)"
task :output do
  name = Socket.gethostname
  local = "-k" if name.include?("local")
  dir = "./ruukinrakennuspalvelu.fi/"
  FileUtils.makedirs dir
  system "cp -R public/* #{dir}"
  system "cd #{dir}; wget -nH #{local} -m http://localhost:3000/"
end
