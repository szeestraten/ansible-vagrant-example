Vagrant.configure(2) do |config|
  config.vm.define "box" do |box|
    # Recommended Ubuntu 16.04 Vagrant box
    box.vm.box = "bento/ubuntu-16.04"

    # Use the Ansible local provisioner to run the playbook.
    # NOTE: This installs Ansible on the VM, and therefore does not require
    # Ansible to be installed on your Vagrant host. See "ansible" provisioner
    # if you want to use Ansible from your Vagrant host.
    box.vm.provision "ansible_local" do |ansible|
      # Which playbook to use
      ansible.playbook = "ansible/example_task.yml"

      # Set Ansible verbose level
      # ansible.verbose = "v"

      # See https://vagrantup.com/docs/provisioning/ansible_common.html for more
      # Ansible options
    end
  end
end
