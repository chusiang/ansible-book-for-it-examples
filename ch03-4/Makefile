# ==============================================================================
#  Author: Chu-Siang Lai / chusiang (at) drx.tw
#  Blog: http://note.drx.tw
#  Filename: Makefile
#  Modified: 2018-05-13 16:55
#  Description: Manage the managed node with Make.
# ==============================================================================

.PHONY: all main show_distro show_pkg_mgr install_vim clean

all: init main run clean

main: show_distro show_pkg_mgr syntax_check run

ci: ci_show_distro ci_show_pkg_mgr syntax_check ci_run

init:
	docker run --name server1 -d -p 2022:22 chusiang/ansible-managed-node:ubuntu-16.04

show_distro:
	ansible all -m setup -a "filter=ansible_distribution*"

ci_show_distro:
	ansible all -m setup -a "filter=ansible_distribution*" -e "ansible_ssh_host=server1 ansible_ssh_port=22"

show_pkg_mgr:
	ansible all -m setup -a "filter=ansible_pkg_mgr"

ci_show_pkg_mgr:
	ansible all -m setup -a "filter=ansible_pkg_mgr" -e "ansible_ssh_host=server1 ansible_ssh_port=22"

syntax_check:
	ansible-playbook --syntax-check install_vim.yml

run:
	ansible-playbook install_vim.yml

ci_run:
	ansible-playbook install_vim.yml -e "ansible_ssh_host=server1 ansible_ssh_port=22"

clean:
	-docker rm -f server1
