build:
	@echo "+ $@"
	sudo docker build \
		--rm=true \
		--no-cache \
		-t rainbowstream:latest .

run:
	@echo "+ $@"
	sudo docker run --rm -it \
		-v ~/.rainbow_oauth:/root/.rainbow_oauth \
		-v ~/.rainbow_config.json:/root/.rainbow_config.json \
		rainbowstream:latest
