# Vagrant virual machine with K3d

Your need install vagrant and virtualbox for up this configuration.

### Step 1

Download box bento/debian-11 for virtualbox from [vagrantup](https://app.vagrantup.com/boxes/search "vagrantup").

### Step 2

Clonr this repository: git clone https://github.com/codesshaman/vagrant_k3d_ondebian.git

### Step 3

Copy box and go inside the repository folder:

``cp ~/Downloads/a22d1053-8311-450b-a740-6e3017c087f8 path_to/vagrant_k3d_ondebian/debian``

``cd vagrant_k3d_ondebian``

### Step 4

Install configuration:

``vagrant up --provider=virtualbox``

### Step 5

Connect:

``ssh vagrant@192.168.58.100``
