Vagrant.configure("2") do |config|

#--------------------------------GitLab CI/CD-----------------------------------------
config.vm.define "gitlab" do |gitlab|
    gitlab.vm.hostname = "GitLab"
    gitlab.vm.box = "generic/centos8s"
    gitlab.vm.network "public_network", bridge: "br0", ip: "192.168.0.170"

    gitlab.vm.provider "virtualbox" do |vb|
        vb.name = "GitLab"
        vb.cpus = 2
        vb.memory = "4096"
    end

     gitlab.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
        systemctl restart sshd.service
        sudo echo "root:toor" | chpasswd
    SHELL
    end
#--------------------------------Web01-----------------------------------------
config.vm.define "web01" do |web01|
    web01.vm.hostname = "web01"
    web01.vm.box = "generic/centos8s"
    web01.vm.network "public_network", bridge: "br0", ip: "192.168.0.171"

    web01.vm.provider "virtualbox" do |vb|
        vb.name = "web01"
        vb.cpus = 1
        vb.memory = "1024"
    end

    web01.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
        systemctl restart sshd.service
        sudo echo "root:toor" | chpasswd
    SHELL
    end
#--------------------------------Web02-----------------------------------------
config.vm.define "web02" do |web02|
    web02.vm.hostname = "web02"
    web02.vm.box = "generic/centos8s"
    web02.vm.network "public_network", bridge: "br0", ip: "192.168.0.172"

    web02.vm.provider "virtualbox" do |vb|
        vb.name = "web02"
        vb.cpus = 1
        vb.memory = "1024"
    end

    web02.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
        systemctl restart sshd.service
        sudo echo "root:toor" | chpasswd
    SHELL
    end
##############################################################
end
