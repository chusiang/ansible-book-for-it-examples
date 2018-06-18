# ==============================================================================
#  Author: Chu-Siang Lai / chusiang (at) drx.tw
#  Blog: https://note.drx.tw
#  Filename: Makefile
#  Modified: 2018-06-18 21:20
#  Description: Run loop script and playbooks.
# ==============================================================================

.PHONY: all main base_loop_script base_loop_playbook adv1_loop adv2_loop clean

all: main clean

main: base_loop_script base_loop_playbook adv1_loop adv2_loop

base_loop_script:
	bash bash_loop.sh
	@echo

base_loop_playbook:
	ansible-playbook playbook_loop.yml
	@echo

adv1_loop:
	ansible-playbook playbook_loop_adv1.yml
	@echo

adv2_loop:
	ansible-playbook playbook_loop_adv2.yml
	@echo

clean:
	-rm -f loop?.yml
