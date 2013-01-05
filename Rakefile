desc "Setup xcode snippets"
task :install do
  user_data_dir = File.join(ENV['HOME'], 'Library/Developer/Xcode/UserData')
  snippets_dir = File.join(user_data_dir, 'CodeSnippets')
  if Dir.exists? user_data_dir
    if Dir.exists? snippets_dir
      print "Directory #{snippets_dir} exists. Would you like to overwrite it? [yn] "
      if $stdin.gets.chomp == 'y'
        puts "Removing previous CodeSnippets"
        system %Q{rm -rf #{snippets_dir}} 
      else
        puts "Canceled"
        exit
      end
    end
  else
    puts "Creating directory #{user_data_dir}" 
    system %Q{mkdir -p #{user_data_dir}}
  end
  puts "Adding symbolic link into #{snippets_dir}"
  system %Q{ln -s "$PWD" #{snippets_dir}}
end

