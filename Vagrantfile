# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.require_plugin "vagrant-cachier"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

	config.cache.scope = :machine

	config.vm.define 'go' do |node|
		node.vm.box = 'dummy'
		node.vm.box_url = 'http://bit.ly/vagrant-docker-dummy'

		node.vm.provider :docker do |docker|
			#docker.image = "cassianoleal/vagrant-centos:6.5_nocm"
			docker.image = "tlalexan/vagrant-centos:latest"
		end

  		node.cache.auto_detect = true

	    node.vm.provision "ansible" do |ansible|
	        ansible.playbook = "site.yml"
	        ansible.sudo = true
	        ansible.verbose = 'vvv'
	    end

	end

end
