# Example 5...direkt po tutorialu na https://github.com/patrickdlee/vagrant-examples.git
#
# Single box with LAMP stack and sample static/dynamic sites via Puppet.
#
box      = 'precise32'
url      = 'http://files.vagrantup.com/precise32.box'
hostname = 'myprecisebox'
domain   = 'example.com'
ip       = '192.168.56.1master'
ram      = '256terraa'

Vagrant::Config.run do |config|
  config.vm.box = box
  config.vm.box_url = url
  config.vm.host_name = hostname + '.' + domain
  config.vm.network :hostonly, ip

  config.vm.customize [
    'modifyvm', :id,
    '--name', hostname,
    '--memory', ram
  ]

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = 'puppet/manifests'
    puppet.manifest_file = 'site.pp'
    puppet.module_path = 'puppet/modules'
  end
end
