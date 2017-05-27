# ansible-pull-testing

## Example Command
```bash
ansible-pull --url=https://github.com/risdenk/ansible-pull-testing --inventory=~/.ansible/pull/$(hostname -f)/hosts --clean --only-if-changed
```

## Examples with Docker
### Matches servers due to hostname
```bash
docker run --rm -it -h testdocker centos:7 bash -c 'yum install -y git python-devel python python-setuptools gcc openssl-devel && easy_install pip && pip install ansible markupsafe && ansible-pull --url=https://github.com/risdenk/ansible-pull-testing --inventory=~/.ansible/pull/$(hostname -f)/hosts --clean --only-if-changed'
```

### Doesn't match servers due to hostname
```bash
docker run --rm -it -h badtestdocker centos:7 bash -c 'yum install -y git python-devel python python-setuptools gcc openssl-devel && easy_install pip && pip install ansible markupsafe && ansible-pull --url=https://github.com/risdenk/ansible-pull-testing --inventory=~/.ansible/pull/$(hostname -f)/hosts --clean --only-if-changed'
```

