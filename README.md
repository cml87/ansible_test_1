# Iximiuz

```bash
PLAY_ID=$(labctl playground list | grep 'ansible_test_1' | awk '{print $1}')
```

```bash
$ labctl playground machines $PLAY_ID
```

```bash
# Terminal 1
labctl ssh-proxy <PLAY_ID> -m cplane-01 --address localhost:2201
```
```bash
ssh -p 2201 -i ~/.ssh/iximiuz_labs_user laborant@127.0.0.1
```

The Iximiuz documentation says that labctl automatically generates the private key `~/.ssh/iximiuz_labs_user` and adds the corresponding public key to the VM's authorized_keys.


# Ansible

```bash
$ ansible-playbook -i inventory/lab_ansible_test_1.yml playbooks/install_docker.yml
```

