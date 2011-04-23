Vagrant::Config.run do |config|
  config.vm.box = "base"

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "my_cookbooks"
    chef.add_recipe "apache"
    %w[apt openssl git ruby rubygems rails mysql mysql::server java].each {|r|
      chef.add_recipe r
    }
    chef.json.merge!({ :mysql => { :server_root_password => "" } })
  end

end
