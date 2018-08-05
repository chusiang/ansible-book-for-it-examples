# ==============================================================================
#  Author: Chu-Siang Lai / chusiang (at) drx.tw
#  Blog: http://note.drx.tw
#  Filename: Makefile
#  Modified: 2018-08-05 21:36
#  Description: Run the managed node and playbook with Make.
# ==============================================================================

.PHONY: all main ci init syntax_check lint_check run ci_run clean

all: 	init main clean

main: syntax_check run

ci: 	syntax_check ci_run

init:
	docker run --name server1 -d -p 32768:22 chusiang/ansible-managed-node:ubuntu-16.04

syntax_check:
	ansible-playbook --syntax-check setup_nginx.yml

lint_check:
	ansible-lint setup_nginx.yml

run:
	ansible-playbook setup_nginx.yml

ci_run:
	ansible-playbook setup_nginx.yml -e "ansible_ssh_host=server1 ansible_ssh_port=22"

clean:
	-docker rm -f server1
