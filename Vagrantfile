Vagrant.configure("2") do |config|
  config.vm.box = "police"
  config.vm.hostname = "police.dev"

  config.vm.network :private_network, ip: "192.168.52.10"
    config.ssh.forward_agent = true

  nfs_setting = RUBY_PLATFORM =~ /darwin/ || RUBY_PLATFORM =~ /linux/
  config.vm.synced_folder ".", "/var/www/police.dev", id: "vagrant-root" , :nfs => nfs_setting

  config.vm.provision :shell, :inline => '/home/vagrant/scripts/police install'

end