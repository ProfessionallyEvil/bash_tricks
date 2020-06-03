# -*- mode: ruby -*-
# vi: set ft=ruby :

$shell_script = 

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "bento/ubuntu-20.04"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "main", type: "shell" do |s|
    s.env = {
      :DEBUG => "true"
    }
    s.inline = <<-SHELL
      # to better understand this go here: https://elrey.casa/bash/scripting/harden
      set -${-//[s]/}eu${DEBUG+xv}o pipefail

      function sys_prep(){
        if command -v docker ; then
          echo 'Docker already exists'
        else
          # prepping system for docker (needed for snap version)
          sudo addgroup --system docker
          sudo adduser vagrant docker

          # look at issue #1 for this repo
          # printf 'installing snap version of docker\n'
          # snap install docker
          # printf 'waiting for docker to start\n'
          # sleep 5

          # TODO: fix snap version
          # read this as to why it is ok: https://blog.elreydetoda.site/curl-bad/ (I did all the steps)
          curl -fsSL 'get.docker.com' | bash
        fi

        # pull container image so user doesn't have to wait
        docker pull bash
      }
      function repo_setup(){
        repo_url='https://github.com/ProfessionallyEvil/bash_tricks'
        local_folder="${repo_url##*/}"
        if [[ -d "${local_folder}" ]] ; then
          echo "repo already exists"
        else
          git clone "${repo_url}"
        fi
        pushd "${local_folder}" || exit 1
        full_path="$(pwd -P)"
        git pull
        popd
      }
      function bash_aliases(){
        printf 'alias pe-bash="docker container run --rm -it -v %s:/bash_tricks -w /bash_tricks bash -- ; ch_perms"' "${full_path}" > ~vagrant/.bash_aliases
        add_newline ~vagrant/.bash_aliases
        type ch_perms | tail -n +2 >> ~vagrant/.bash_aliases
      }
      function ch_perms(){
        sudo chown -R vagrant:vagrant ~vagrant
      }
      function add_newline(){
        echo >> "${1}"
      }
      function main(){
        sys_prep
        repo_setup
        bash_aliases
        ch_perms
      }
      main
    SHELL
  end
end
