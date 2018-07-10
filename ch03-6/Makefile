# ==============================================================================
#  Author: Chu-Siang Lai / chusiang (at) drx.tw
#  Blog: https://note.drx.tw
#  Filename: Makefile
#  Modified: 2018-06-20 00:59
#  Description: Run template demo playbooks.
# ==============================================================================

.PHONY: all main template_demo template_demo_ansible template_demo_Day14 template_demo2 template_demo2_test template_demo2_production clean

all: main clean

main: lab1 lab2

lab1: template_demo template_demo_ansible template_demo_Day14

template_demo:
	ansible-playbook template_demo.yml
	@echo

template_demo_ansible:
	ansible-playbook template_demo.yml -e "dynamic_word=ansible"
	@echo

template_demo_Day14:
	ansible-playbook template_demo.yml --extra-vars "dynamic_word=Day14"
	@echo

lab2: template_demo2 template_demo2_test template_demo2_production

template_demo2:
	ansible-playbook template_demo2.yml
	@echo

template_demo2_test:
	ansible-playbook template_demo2.yml -e "env=test"
	@echo

template_demo2_production:
	ansible-playbook template_demo2.yml -e "env=production"
	@echo

clean:
	-rm -f hello_world.txt
