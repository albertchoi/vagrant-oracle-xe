Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu-1110-server-amd64"
    config.vm.box_url = "http://timhuegdon.com/vagrant-boxes/ubuntu-11.10.box"
    config.vm.hostname = "oraxe"
    config.vm.network :private_network, ip: "192.168.50.3"
    config.vm.network :forwarded_port, guest: 22, host: 41022
    config.vm.provision :puppet, :module_path => "modules", :options => "--verbose --trace" do |puppet|
      puppet.manifests_path = "manifests"
      puppet.manifest_file  = "site.pp"
    end
    config.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "1024"]
    end
    #config.vm.boot_mode = :gui

end
