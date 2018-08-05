# ==============================================================================
#  Author: Chu-Siang Lai / chusiang (at) drx.tw
#  Blog: http://note.drx.tw
#  Filename: Makefile
#  Modified: 2018-08-05 16:55
#  Description: Run the managed node and playbook with Make.
# ==============================================================================

.PHONY: all main init syntax_check lint_check run clean

all: main clean

main: init syntax_check run

init:
	docker run --name server1 -d -p 32768:22 chusiang/ansible-managed-node:ubuntu-16.04

syntax_check:
	ansible-playbook --syntax-check setup_nginx.yml

lint_check:
	ansible-lint setup_nginx.yml

run:
	ansible-playbook setup_nginx.yml

clean:
	-docker rm -f server1
