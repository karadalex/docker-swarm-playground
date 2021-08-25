Vagrant.configure("2") do |config|

  config.vm.define "manager1" do |manager1|
    manager1.vm.box = "hashicorp/bionic64"  
    manager1.vm.provision "docker",    
      images: ["ubuntu"]
    manager1.vm.network "private_network", ip: "192.168.99.100"
  end

  config.vm.define "worker1" do |worker1|
    worker1.vm.box = "hashicorp/bionic64"
    worker1.vm.provision "docker",    
      images: ["ubuntu"]
    worker1.vm.network "private_network", ip: "192.168.99.101"
  end

  config.vm.define "worker2" do |worker2|
    worker2.vm.box = "hashicorp/bionic64"   
    worker2.vm.provision "docker",    
      images: ["ubuntu"]
    worker2.vm.network "private_network", ip: "192.168.99.102"
  end

end
