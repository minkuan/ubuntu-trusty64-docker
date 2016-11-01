# 目标
ubuntu trusty64 with docker vagrant box

# 步骤
1. vagrant ubuntu/trusty64 base box
2. vagrant docker provision
3. virtualbox linux guest additions
	- 安装光盘，加载/usr/share/virtualbox/VBoxGuestAdditions.iso
	- mount /dev/cdrom /mnt
	- sudo /mnt/VBoxGuestAddions.run
4. 打包新box
	- vagrant package --base {UUID} --output ./ubuntu-trusty64-docker.box

