Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/focal64"
    
    config.vm.define "k3s-master" do |master|
      master.vm.hostname = "k3s-master"
      master.vm.network "private_network", ip: "192.168.56.10"
      master.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
        vb.cpus = 4
      end
    end
    
    (1..2).each do |i|
      config.vm.define "k3s-worker-#{i}" do |worker|
        worker.vm.hostname = "k3s-worker-#{i}"
        worker.vm.network "private_network", ip: "192.168.56.#{10+i}"
        worker.vm.provider "virtualbox" do |vb|
          vb.memory = "2048"
          vb.cpus = 2
        end
      end
    end
  end
  