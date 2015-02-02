# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"
#
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  #
  config.vm.box = "ubuntu/trusty64"
  # Create a forwarded port mapping which allows access to a specific port
  # In the exemple below accessing "localhost:8001" will access port 80 on the guest machine
  config.vm.network "forwarded_port", guest: 80, host: 8001
  #
  config.vm.synced_folder ".", "/vagrant",
  owner: "vagrant", group: "vagrant",
  mount_options: ["dmode=777","fmode=777"]
  #
  # Use VBoxManage to customize the VM.
  config.vm.provider "virtualbox" do |v|
    v.name = "ubuntu-trusty64-wp"
    v.memory = 512
  end
  # Enable provisioning with ANSIBLE, specifying a playbook path (relative to this Vagrantfile).
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "vagrant-wp.yml"
  end
end
