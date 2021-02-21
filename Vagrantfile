# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ".git/"

  config.vm.provider :libvirt do |libvirt|
    # Enable KVM nested virtualization
    libvirt.nested = true
    libvirt.cpu_mode = "host-passthrough"

    libvirt.volume_cache = 'unsafe'
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
  end
end
