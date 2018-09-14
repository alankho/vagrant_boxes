Vagrant.configure("2") do |config|
  config.vm.define :database do |database|
    database.vm.box = "ubuntu/trusty64"
    database.vm.network :private_network, ip: "192.168.200.100"
    database.vm.hostname = "dockerlab.local"
    #database.vm.provision :shell, path: "provision-database", args: ENV['ARGS']
    database.vm.synced_folder "shared/", "/home/vagrant/shared", create: true

    database.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--cpus", "1", "--memory", 2048]
    end
  end

end
