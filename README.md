# 目标
vagrant box of ubuntu/trusty64 with docker & virtualbox guest additions provisioned.

# 步骤
1. vagrant ubuntu/trusty64 base box
2. vagrant docker provision
3. virtualbox linux guest additions
	- 安装光盘，加载/usr/share/virtualbox/VBoxGuestAdditions.iso
	- mount /dev/cdrom /mnt
	- sudo /mnt/VBoxGuestAddions.run
4. 打包新box
	- vagrant package --base {UUID} --output ./ubuntu-trusty64-docker.box

# 问题及解决
1. vagrant ssh authentication failure

	- ssh-keygen生成vagrant/vagrant公钥和私钥
	- 起动ssh-agent
	- ssh-add加入vagrant私钥
	- rm -f ~/.vagrant.d/inscure_key_file
