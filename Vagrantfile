
#
# Vagrantfile for DevOps Test
#

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "geerlingguy/centos7"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.cpus = 4
  end

  #
  # Ansible Hub (ans05.dev)
  #

  config.vm.define "ans05.dev" do |ans05|

    ans05.vm.hostname = "ans05.dev"
    ans05.vm.network :private_network, ip: "192.168.168.101"

    ans05.vm.provider :virtualbox do |v|
      v.name = "ans05.dev"
      v.memory = 1024
    end

     ans05.vm.provision :ansible do |ansible|
       ansible.playbook = "provisioning/ansible/ans.yml"
       ansible.sudo = true
     end

     ans05.vm.synced_folder "./ansible/", "/usr/local/ansible"
  end


  #
  # Server Ansible controlled (svr05.dev)
  #

   config.vm.define "svr05.dev" do |svr05|

     svr05.vm.hostname = "svr05.dev"
     svr05.vm.network :private_network, ip: "192.168.168.102"

     svr05.vm.provider :virtualbox do |v|
       v.name = "svr05.dev"
       v.memory = 2048
     end

     svr05.vm.provision :ansible do |ansible|
       ansible.playbook = "provisioning/ansible/svr.yml"
       ansible.sudo = true
     end
   end

end
