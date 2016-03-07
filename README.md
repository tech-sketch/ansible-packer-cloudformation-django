# ansible-packer-cloudformation-django

## Summary

deploy django application to aws using ansible, packer and cloudformation

## Requirement

* ansible >= 2.0
* packer >= 0.9
* Django >= 1.8

## How To Use

```
$ git clone https://github.com/tech-sketch/ansible-packer-cloudformation-django.git
$ cd ~/ansible-packer-cloudformation-django/packer/
$ packer build django.json
$ cd ~/ansible-packer-cloudformation-django/playbook/
$ sed -i -e 's/^      ami:.*$/      ami: "<created ami id>"/g' ./group_vars/all.yml
$ sed -i -e 's/^      keyname:.*$/      keyname: "<your keypair name>"/g' ./group_vars/all.yml
$ sed -i -e 's/^      password:.*$/      password: "<database password>"/g' ./group_vars/all.yml 
$ ansible-playbook -i hosts/ec2.py cloudformation.yml 
```

## for more detail

See this page [http://tech-sketch.jp/2016/03/ansible-packer-cloudformation-djangoo.html](http://tech-sketch.jp/2016/03/ansible-packer-cloudformation-django.html)

## License

[MIT License](https://github.com/tech-sketch/ansible-packer-cloudformation-django/blob/master/LICENSE)
