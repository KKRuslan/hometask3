# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/focal64"


  if Vagrant.has_plugin?("vagrant-vbguest") then
    config.vbguest.auto_update = false
  end

  config.vm.provision "shell", inline: <<-SHELL
    cp /vagrant/mycron /etc/cron.d/
    cp /vagrant/sysinfo.sh /root/
    chmod +x /root/sysinfo.sh
    systemctl restart cron
  SHELL
end