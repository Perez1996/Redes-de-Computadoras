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
	make DefaultGw
	
DefaultGw:
	docker exec -ti --privileged protocoloospf_h1_1 route add default gw 192.168.1.10
	docker exec -ti --privileged protocoloospf_h2_1 route add default gw 192.168.1.10
	docker exec -ti --privileged protocoloospf_h3_1 route add default gw 192.168.1.10
	docker exec -ti --privileged protocoloospf_h4_1 route add default gw 192.168.8.10
	docker exec -ti --privileged protocoloospf_h5_1 route add default gw 192.168.9.10

h1:
	docker exec -ti protocoloospf_h1_1 ash
h2:
	docker exec -ti protocoloospf_h2_1 ash
h3:
	docker exec -ti protocoloospf_h3_1 ash
h4:
	docker exec -ti protocoloospf_h4_1 ash
h5:
	docker exec -ti protocoloospf_h5_1 ash

trace_r1r4:
	docker exec -ti protocoloospf_h1_1 traceroute 192.168.8.11
trace_r1r5:
	docker exec -ti protocoloospf_h1_1 traceroute 192.168.9.11

ospfr1:
	telnet localhost 10012

ospfr2:
	telnet localhost 10014

ospfr3:
	telnet localhost 10016

ospfr4:
	telnet localhost 10018

ospfr5:
	telnet localhost 10020

adminr1:
	telnet localhost 10011

adminr2:
	telnet localhost 10013

adminr3:
	telnet localhost 10015

adminr4:
	telnet localhost 10017

adminr5:
	telnet localhost 10019