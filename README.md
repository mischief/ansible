# OpenBSD router with Ansible

## Setup

1. install openbsd
2. put `permit nopass keepenv :wheel` in /etc/doas.conf
3. install python3

	doas pkg_add -vi python

## execute

	ansible-playbook --syntax-check router.yaml && \
		ansible-playbook --ask-vault-password -e @secrets.yaml --become router.yaml

## tip: test a template locally

	ansible all -i localhost, -c local -m template \
		-a "src=roles/router/templates/pf.conf.j2 dest=./test.txt" \
		--extra-vars=@group_vars/router.yaml

