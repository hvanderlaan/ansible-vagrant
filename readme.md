# ansible - vagrant development stub
this is a development stub for ansible and vagrant. with this stub you can test very fast your ansible playbooks / roles on your local unix/linux machine.

### requirements ansible
for running ansible on your local machine you need the have python2.7 installed. if python2.7 is installed you can follow this installation guide.
```bash
curl -sSL https://bootstrap.pypa.io/get-pip.py > get-pip.py
python get-pip.py || sudo -H python get-pip.py
```

after this you can install the latest version of ansible via pip
```bash
sudo -H pip install pip --upgrade
sudo -H pip install ansible --upgrade
```

### other requirements
for vagrant to work you need a provider, virtualbox provider is the free one so we will go with that. you need to download [virtualbox][1] and [vagrant][2].

### usage
```bash
# generate sshkeys if you don't have them
ssh-keygen
# placeing the ssh keys
cp ~/.ssh/id_rsa.pub ansible-vagrant/vagrant/template/files/public.rsa.ket
vi ansible-vagrant/ansible/ansible.cfg
  # enter location of private key at the last entry
```
```bash
cd ansible-vagrant/vagrant/template
vagrant up
cd ../../ansible
ansible vagrant -m ping
ansible vagrant -m ping -b
```

[1]: https://www.virtualbox.org/wiki/Downloads
[2]: https://www.vagrantup.com/downloads.html
