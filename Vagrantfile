# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.define :hub do |hub|
    hub.vm.network "private_network", type: "dhcp"

    hub.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "hub.yml"
    end
  end

  config.vm.define :node_firefox do |node_firefox|
    node_firefox.vm.network "private_network", type: "dhcp"

    node_firefox.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "firefox.yml"
    end
  end

  config.vm.define :node_chrome do |node_chrome|
    node_chrome.vm.network "private_network", type: "dhcp"

    node_chrome.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "chrome.yml"
    end
  end
end
