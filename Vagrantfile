# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
  config.vm.provision :shell do |shell|
    shell.inline = "sed -i 's#us.archive.ubuntu.com#mirrors.163.com#' /etc/apt/sources.list && apt-get update && apt-get -y install git vim-gtk libxml2-dev libxslt1-dev libpq-dev python-pip libsqlite3-dev && apt-get -y build-dep python-mysqldb && pip install git-review tox && git clone git://git.openstack.org/openstack-dev/devstack && chown -R vagrant:vagrant devstack && git clone https://github.com/progresstudy/dotfiles.git && chown -R vagrant:vagrant dotfiles"
  end
  config.vm.network :forwarded_port, guest: 80, host: 10080
end
