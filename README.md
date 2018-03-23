# One user, one ruby

>Build a simple environment with Ruby

## Usage example

```
export TF_VAR_do_token="$(lpass show --notes do_token)"
lpass logout -f
ssh-keygen -q -b 2048 -t rsa -N '' -f id_rsa
```

```
terraform apply
ansible-playbook playbook.yml
```

```
ip=$(terraform output | awk '/ip/ { print $NF }')
ssh -i id_rsa root@$ip ruby --version
ssh -i id_rsa foo@$ip ruby --version
```

```
terraform destroy -force
rm *.tfstate* id_rsa*
```

## Links

* https://blog.arkency.com/2012/11/one-app-one-user-one-ruby/
* https://github.com/postmodern/ruby-install/issues/223#issuecomment-167700861
* https://ansibledaily.com/idempotent-shell-command-in-ansible/