Vagrant.configure("2") do |config|
  config.vm.define "miniapp" do |miniapp|
    miniapp.vm.box = "bento/ubuntu-22.04"
    miniapp.vm.box_check_update = false
    miniapp.vm.network "forwarded_port", guest: 3306, host: 3306 
    miniapp.vm.network "private_network", ip: "192.168.33.10"
    miniapp.vm.synced_folder "./miniapp", "/vagrant_data"

    miniapp.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "1024"
      vb.name = "miniapp"
    end
  end
end
