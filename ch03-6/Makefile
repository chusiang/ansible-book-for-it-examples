# ==============================================================================
#  Author: Chu-Siang Lai / chusiang (at) drx.tw
#  Blog: https://note.drx.tw
#  Filename: Makefile
#  Modified: 2018-06-20 00:59
#  Description: Run template demo playbooks.
# ==============================================================================

.PHONY: all main template_demo1 template_demo2 template_demo3 clean

all: main clean

main: template_demo1 template_demo2 template_demo3

template_demo1:
	ansible-playbook template_demo.yml
	@echo

template_demo2:
	ansible-playbook template_demo.yml -e "dynamic_word=ansible"
	@echo

template_demo3:
	ansible-playbook template_demo.yml --extra-vars "dynamic_word=Day14"
	@echo

clean:
	-rm -f hello_world.txt
