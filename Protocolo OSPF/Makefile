build:  
	docker-compose build
        
setup:
	@echo "\n\e[1m\e[32m-- Mounting containers --\e[22m\e[24m\e[39m"
	docker-compose up -d

clean:
	@echo "\n\e[1m\e[32m-- Removing containers --\e[22m\e[24m\e[39m"
	docker-compose down

run: 
	make clean
	make build
	make setup
