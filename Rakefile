require 'rubygems'
require 'rake'
# require 'fileutils'

desc "Create new .env file"
task :create_env_file do
  puts "Which branch?"
  branch = STDIN.gets.chomp
  
  
  # both are hardcoded. find out the current branch from git
  base_path = "http://raw.github.com/spier/yql-tables/raw/#{branch}/"
  env_filename = "alltables_forked.env"
  env_fh = File.open(env_filename,"w")
  
  # write all .xml files to .env file
  xml_files = Dir.glob("**/*.xml")
  xml_files.each do |filename| 
    table_name = File.basename(filename,".xml")
    absolute_url = File.join(base_path,filename)
    use_statement = "USE '#{absolute_url}' AS #{table_name};"
    env_fh.puts use_statement
  end
  
  env_fh.close()
  puts "Wrote new file #{env_filename}. Total of #{xml_files.size} YQL open data tables."
end

task :default => :create_env_file
