DIR := ${CURDIR}

build:
	@echo "+ $@"
	docker build -t vim:latest .

run:
	@echo "+ $@"
	docker run --rm -it \
		-v $(DIR):/root/workspace \
		vim:latest
