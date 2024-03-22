ENV['VAGRANT_NO_PARALLEL'] = 'yes'

Vagrant.configure("2") do |config|

  config.vm.provision "shell", path: "bootstrap.sh"

  NodeCount = 1

  (1..NodeCount).each do |i|
    config.vm.define "devops#{i}" do |node|
      node.vm.box = "ubuntu/jammy64"
      node.vm.hostname = "devops#{i}"
      node.vm.network "public_network", type: "bridge"

      node.vm.provider "virtualbox" do |vb|
        vb.cpus = "4"
        vb.memory = "4096"

      end
    end
  end
end
