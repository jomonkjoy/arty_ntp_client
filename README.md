
<h2>FPGA-based NTP client</h2><br><br>

This is a simple NTP client running at the Digilent Arty-7 35T FPGA board.<br><br>
Every four seconds an NTP packet is sent to the NTP server. The response from the server contains the timestamp on departure (64-bit number) which is used to set local time of NTP client. When NTP client receives valid NTP packet the green LED is lit, timeout error is indicated 
by red LED. NTP client contains minimal implementation of UDP/IP stack with handling ARP requests. The data are send over Fast Ethernet throught MII interface. No checksum calculation on incoming IPv4 and UDP packets.
Current time is displayed on 7-seg display.
<br><br>
Used IP cores/VHDL code:
- FIFO from Xilinx
- AXI4-Stream switchboard from Xilinx
- Code for Ethernet CRC32 calculation and 7seg dispplay: Mike Field  (http://hamsterworks.co.nz/)
- UART implementation: https://www.nandland.com/vhdl/modules/module-uart-serial-port-rs232.html
<br><br>

 ![alt text](https://github.com/filipamator/arty_ntp_client/blob/master/doc/diagram.PNG?raw=true)
