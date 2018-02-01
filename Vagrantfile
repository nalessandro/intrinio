# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-16.04"

  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y python-pandas python-pip ipython-notebook

    # Intrinio authentication environment variables
    tee "/etc/profile.d/intrinio-auth.sh" > "/dev/null" <<EOF
    export INTRINIO_USERNAME=#{ENV['INTRINIO_USERNAME']}
    export INTRINIO_PASSWORD=#{ENV['INTRINIO_PASSWORD']}
    EOF
  SHELL
end
