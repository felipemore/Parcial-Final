# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
 config.vm.define :cliente do |cliente|
 cliente.vm.box = "bento/centos-7.8"
 cliente.vm.network :private_network, ip: "192.168.50.1"
 cliente.vm.hostname = "cliente"
 end
 config.vm.define :servidor do |servidor|
 servidor.vm.box = "bento/centos-7.8"
 servidor.vm.network :private_network, ip: "192.168.50.3"
 servidor.vm.network :forwarded_port, guest: 80, host:5567
 servidor.vm.network :forwarded_port, guest: 443, host:5568
 servidor.vm.hostname = "servidor"
 end
 config.vm.define :servidor2 do |servidor2|
 servidor2.vm.box = "bento/centos-7"
 servidor2.vm.network :private_network, ip: "192.168.50.4"
 servidor2.vm.network :forwarded_port, guest: 443, host:5568
 servidor2.vm.hostname = "servidor2"
 end
 config.vm.define :servidorRestMySQL do |servidorRestMySQL|
 servidorRestMySQL.vm.box = "bento/centos-7"
 servidorRestMySQL.vm.network :private_network, ip: "192.168.50.5"
 servidorRestMySQL.vm.provision "file", source: "apirest_mysql.py", destination: "/home/vagrant/apirest_mysql.py"
 servidorRestMySQL.vm.provision "file", source: "init.sql", destination: "/home/vagrant/init.sql"
 servidorRestMySQL.vm.provision "shell", path: "script.sh"
 servidorRestMySQL.vm.hostname = "servidorRestMySQL"
 end
 config.vm.define :servidorwp1 do |servidorwp1|
 servidorwp1.vm.box = "bento/centos-7.8"
 servidorwp1.vm.network :private_network, ip: "192.168.50.15"
 servidorwp1.vm.hostname = "servidorwp1"
 end
 config.vm.define :servidorwp2 do |servidorwp2|
 servidorwp2.vm.box = "bento/centos-7"
 servidorwp2.vm.network :private_network, ip: "192.168.50.16"
 servidorwp2.vm.hostname = "servidorwp2"
 end
 config.vm.define :proxy do |proxy|
 proxy.vm.box = "bento/centos-7"
 proxy.vm.network :private_network, ip: "192.168.50.17"
 proxy.vm.hostname = "proxy"
 end
 config.vm.define :servidorSTRM do |servidorSTRM|
 servidorSTRM.vm.box = "bento/centos-7"
 servidorSTRM.vm.provision "shell", path: "stream.sh"
 servidorSTRM.vm.network :private_network, ip: "192.168.50.10"
 servidorSTRM.vm.hostname = "servidorSTRM"
 end
 config.vm.define :firewallSTRM do |firewallSTRM|
 firewallSTRM.vm.box = "bento/centos-7"
 firewallSTRM.vm.provision "shell", path: "firewallscript.sh"
 firewallSTRM.vm.network :private_network, ip: "209.191.50.1"
 firewallSTRM.vm.network :public_network, bridge: "Intel(R) Dual Band Wireless-N 7260", ip: "192.168.1.66"  
 firewallSTRM.vm.hostname = "firewallSTRM"
 end
end
#config.vm.define :servidorCF do |servidorCF|
#servidorCF.vm.box = "bento/centos-7"
#servidorCF.vm.network :public_network, bridge: "Intel(R) Dual Band Wireless-N 7260", ip: "192.168.1.63"
#servidorCF.vm.network :private_network, ip: "192.168.50.4"#
#servidorCF.vm.network :forwarded_port, guest: 80, host:55637
#servidorCF.vm.network :forwarded_port, guest: 443, host:5568
#servidorCF.vm.hostname = "servidorCF"
#end
#end
# config.vm.define :clienteFw do |clienteFw|
# clienteFw.vm.box = "bento/centos-7"
# clienteFw.vm.network :private_network, ip: "192.168.50.2"
# clienteFw.vm.hostname = "clienteFw"
# end
# config.vm.define :firewall do |firewall|
# firewall.vm.box = "bento/centos-7"
# firewall.vm.network :private_network, ip: "209.191.50.3"
# firewall.vm.network :private_network, ip: "192.168.50.3"
# firewall.vm.hostname = "firewall"
# end


