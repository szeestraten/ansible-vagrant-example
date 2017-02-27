Vagrant.configure(2) do |config|
  config.vm.define "box" do |box|
    # Recommended Ubuntu 16.04 Vagrant box
    box.vm.box = "bento/ubuntu-16.04"

    # Set the hostname of the VM
    box.vm.hostname = "demobox"

    # Forward port 80 on VM to 8080 to the Vagrant host
    box.vm.network "forwarded_port", guest: 80, host: 8080

    # Use the Ansible local provisioner to run the playbook.
    # NOTE: This installs Ansible on the VM, and therefore does not require
    # Ansible to be installed on your Vagrant host. See "ansible" provisioner
    # if you want to use Ansible from your Vagrant host.
    box.vm.provision "ansible_local" do |ansible|
      # Which playbook to use
      ansible.playbook = "ansible/deploy.yml"

      # Example of how to add extra Ansible vars for development environment
      ansible.extra_vars = {
        is_vagrant: "True"
      }

      # Set Ansible verbose level
      # ansible.verbose = "v"

      # See https://vagrantup.com/docs/provisioning/ansible_common.html for more
      # Ansible options
    end
  end
end
