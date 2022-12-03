# -*- mode: ruby -*-
# vi: set ft=ruby :

# create machines config
Vagrant.configure(2) do |config|
    config.vm.box = "bento/debian-11"
    config.vm.provider "virtualbox" do |v|
    config.vm.synced_folder ".", "/mnt", type: "virtualbox"
        # for connect with SSH on both machines with no password
        id_rsa_pub = File.read("#{Dir.home}/.ssh/id_rsa.pub")
        config.vm.provision "copy ssh public key", type: "shell",
        inline: "echo \"#{id_rsa_pub}\" >> /home/vagrant/.ssh/authorized_keys"
    end

  # master node config
    config.vm.define 'debian' do |debian|
        debian.vm.hostname = "debian-k3d"
        debian.vm.provision "shell",
        privileged: true, path: "setup.sh"
        debian.vm.provider "virtualbox" do |v|
            v.name = "debian_k3d"
            v.memory = 4096
            v.cpus = 4
        end
    end

end
