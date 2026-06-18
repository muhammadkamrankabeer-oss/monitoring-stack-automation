# Vagrantfile for Monitoring Stack Automation Project

#

# This VM hosts:

# - Prometheus

# - Grafana

# - Alertmanager

# - Node Exporter

#

# Purpose:

# Build a reproducible monitoring lab using

# Infrastructure as Code (IaC).

Vagrant.configure("2") do |config|

# Debian 12 Bookworm base image

config.vm.box = "debian/bookworm64"

# Hostname inside VM

config.vm.hostname = "monitoring-stack-vm"

# Host-only private network

config.vm.network "private_network",
ip: "192.168.56.20"

# Grafana

config.vm.network "forwarded_port",
guest: 3000,
host: 3000

# Prometheus

config.vm.network "forwarded_port",
guest: 9090,
host: 9090

# Alertmanager

config.vm.network "forwarded_port",
guest: 9093,
host: 9093

# Shared repository folder

config.vm.synced_folder ".",
"/home/vagrant/monitoring-stack"

# VM resources

config.vm.provider "virtualbox" do |vb|
vb.name   = "monitoring-stack"
vb.memory = "4096"
vb.cpus   = 2
end

# Install Docker automatically

config.vm.provision "shell", inline: <<-SHELL

apt-get update -y

apt-get install -y \
  apt-transport-https \
  ca-certificates \
  curl \
  gnupg \
  lsb-release

curl -fsSL https://download.docker.com/linux/debian/gpg \
  | gpg --dearmor \
  -o /usr/share/keyrings/docker-archive-keyring.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" \
  > /etc/apt/sources.list.d/docker.list

apt-get update -y

apt-get install -y \
  docker-ce \
  docker-ce-cli \
  containerd.io \
  docker-buildx-plugin \
  docker-compose-plugin

usermod -aG docker vagrant

SHELL

end
