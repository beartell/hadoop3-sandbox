Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provision "docker" do |d|
    d.run "xentnex/hadoop:v3.0.0"
  end
end

