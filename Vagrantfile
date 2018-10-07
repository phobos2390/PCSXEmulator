Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.ssh.forward_agent = true
  config.ssh.forward_x11 = true
  #config.vm.provision :shell, name: "Setup-Display", privileged: false, inline: <<-SHELL
  #  export DISPLAY="#{ENV['DISPLAY']}"
  #  echo "export DISPLAY='$DISPLAY'" >> /home/vagrant/.bash_profile
  #SHELL
  config.vm.provision :shell, name: "yum-downloads", privileged: false, inline: <<-SHELL
    sudo yum install -y zlib*.i686
    curl http://www.epsxe.com/files/ePSXe205linux.zip -Lo ePSXe.zip 
    mkdir epsxe
    pushd epsxe
    unzip ePSXe.zip
    popd
  SHELL
end
