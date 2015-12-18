# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.define :hub do |hub|
    hub.vm.network :forwarded_port, guest: 4444, host: 4444
    hub.vm.network "private_network", ip: "192.168.12.13"

    hub.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbooks/selenium-hub.yml"
    end
  end

  config.vm.define :firefox do |firefox|
    firefox.vm.network "private_network", ip: "192.168.12.14"

    firefox.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbooks/selenium-node-firefox.yml"
    end
  end

  config.vm.define :chrome do |chrome|
    chrome.vm.network "private_network", ip: "192.168.12.15"

    chrome.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbooks/selenium-node-chrome.yml"
    end
  end
end
