control_node_cores = 1
control_node_mem = 4
control_node_ip = "192.168.60.2"

worker_nodes = 2
worker_node_cores = 2
worker_node_mem = 6
worker_node_ip_base = "192.168.61"


Vagrant.configure("2") do |config|
    config.vm.box = "bento/ubuntu-24.04"
    config.vm.box_version = "202404.26.0"

    # I know this is bad but I cannot get it to work with SSH when running vagrant up.
    config.ssh.password = "vagrant"

    config.vm.define "control-node" do |control_node|
        control_node.vm.network "private_network", ip: control_node_ip
        control_node.vm.provider "virtualbox" do |vb|
            vb.memory = control_node_mem * 1024
            vb.cpus = control_node_cores
        end
    end
    (1..worker_nodes).each do |i|
        config.vm.define "worker-node-#{i}" do |worker_node|
            worker_node.vm.network "private_network", ip: worker_node_ip_base + ".#{i + 1}"
            worker_node.vm.provider "virtualbox" do |vb|
                vb.memory = worker_node_mem * 1024
                vb.cpus = worker_node_cores
            end
        end
    end
end



