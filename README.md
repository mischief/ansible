# OpenBSD router with Ansible

## Setup

1. install openbsd
2. put `permit nopass keepenv :wheel` in /etc/doas.conf
3. install python3

	doas pkg_add -vi python

## execute

	ansible-playbook --syntax-check router.yaml && \
		ansible-playbook --become router.yaml

