include ../utils/Makefile.help
include ../utils/Makefile.functions

export NAME := prometheus

test: ##@targets Starts docker compose.
	docker-compose -p $(NAME) -f test.yaml up
.PHONY: test

rm:
	docker-compose -p $(NAME) -f test.yaml stop
.PHONY: rm

clean: rm
	docker-compose -p $(NAME) -f test.yaml rm -f
	sudo rm -rf root
	rm -rf log.txt
.PHONY: clean

setup:
	mkdir -p root/icinga2
	mkdir -p root/icingaweb2
	mkdir -p root/icingadb
	mkdir -p root/icingawebdb
	mkdir -p root/html
	sudo chown 102.103 -R root/icinga2
	sudo chown 33.33 -R root/icingaweb2
	sudo chmod o+rwX root/icingadb
	sudo chmod o+rwX root/icingawebdb
	sudo chown 33.33 -R root/html
.PHONY: setup
