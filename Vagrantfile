# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
# install jenkins-debian-glue
# see http://jenkins-debian-glue.org/getting_started/automatic/
wget --no-check-certificate https://raw.github.com/mika/jenkins-debian-glue/master/puppet/apply.sh
sudo bash ./apply.sh vagrant
SCRIPT

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.hostname = "jenkins.example.org"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provision "shell", inline: $script
end
