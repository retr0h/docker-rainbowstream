build:
	@echo "+ $@"
	sudo docker build -t rainbowstream:latest .

run:
	@echo "+ $@"
	sudo docker run --rm -it \
		-v ~/.rainbow_oauth:/root/.rainbow_oauth \
		rainbowstream:latest
