Vagrant.configure("2") do |config|
 if Vagrant.has_plugin? "vagrant-vbguest"
 config.vbguest.no_install = true
 config.vbguest.auto_update = false
 config.vbguest.no_remote = true
 end
 config.vm.define :cliente do |cliente|
 cliente.vm.box = "centos/stream8"
 cliente.vm.network :private_network, ip: "192.168.50.2"
 cliente.vm.hostname = "cliente"
 end
 config.vm.define :servidor do |servidor|
 servidor.vm.box = "centos/stream8"
 servidor.vm.network :private_network, ip: "192.168.50.3"
 servidor.vm.network :forwarded_port, guest: 80, host:5567
 servidor.vm.network :forwarded_port, guest: 443, host:5568
servidor.vm.hostname = "servidor"
 end

config.vm.define :clienteFw do |clienteFw|
 clienteFw.vm.box = "centos/stream8"
 clienteFw.vm.network :private_network, ip: "209.191.100.2"
 clienteFw.vm.hostname = "clienteFw"
 end
 config.vm.define :firewall do |firewall|
 firewall.vm.box = "centos/stream8"
 firewall.vm.network :private_network, ip: "209.191.100.3"
 firewall.vm.network :private_network, ip: "192.168.100.3"
firewall.vm.network :forwarded_port, guest: 80, host: 5571
firewall.vm.network :forwarded_port, guest: 443, host: 5572
 firewall.vm.hostname = "firewall"
 end
 config.vm.define :servidor2 do |servidor2|
 servidor2.vm.box = "centos/stream8"
 servidor2.vm.network :private_network, ip: "192.168.100.4"
servidor2.vm.network :forwarded_port, guest: 80, host: 5569
servidor2.vm.network :forwarded_port, guest: 443, host: 5570

 servidor2.vm.hostname = "servidor2"
 end

end