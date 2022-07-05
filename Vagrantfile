# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ".git/"

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "generic/ubuntu2004"
  end

  config.vm.define "rocky" do |rocky|
    rocky.vm.box = "generic/rocky8"
  end

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
