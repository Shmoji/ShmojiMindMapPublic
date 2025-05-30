  * what is it? #memo ^hDn8eTiNC
    * local device IP addresses: your router assigns IP addresses to devices on your local network using DHCP (e.g., 192.168.x.x or 10.0.x.x)
      * DYNAMIC: these are dynamic by default and can change unless you set them to not change
        * Q: how often do they change?
          * depends on your network and your ISP. 
          * GPT4o:
            * **when a device reconnects to the network**: If a device disconnects and reconnects (e.g., after being turned off), it might receive a different local IP address, depending on the DHCP settings and the lease time.
            * **When the router is restarted**: Restarting the router can cause it to reassign IP addresses to devices.
            * **DHCP Lease Expiration**: Similar to public IPs, local IPs are assigned with a lease time, after which the IP can change.
              * Q: is lease time just a timer?
                * Yes
        * can go to network settings in ur device to make local IP stay static
      * NOT PUBLIC: They are not public and are only used within your local network. External systems on the internet cannot directly access these local IP addresses due to Network Address Translation (NAT) provided by your router. NOTE: NAT maps privIPs to pubIP - no MAC addresses involved
    * public IP address: IP address assigned to your network by your Internet Service Provider (ISP)
      * DYNAMIC: these are dynamic by default and can change unless you set them to not change
        * can use DDNS to keep static public IP
      * PUBLIC: visible to the internet and can be used to identify your network. However, individual devices on your network usually share this public IP when accessing external sites or services.
  * how TOs
    * how to set static local device IP address on UBUNTU
	    * in terminal: ip addr show
	        * beside line under enp4s0 with "inet" it will say "dynamic" if this is still a dynamic ip address device
	        * also, the address right after "inet" is your ip address (without the slash) - will be your static ip after you set it
	* there's a lot of confusing rules for coming up with static ip - but i just decided to take current one and add 100 to the end - and make sure it's over 200 - bc internet said over 200 usuallyyy isnt used
	* you can use "ping 192.168.1.x" to check if in use or not. i think the first line always returns data, but then youll know after that or not
	* gateway is usually the default you know of 192.168.1.1 - but can also use "ip route | grep default" to find out - it's the first ip you see
	* you can find DNS in "Details" tab of Ubuntu netty settings - if multiple then put commas
	* turn network off and on again
	* use ip addr show again to validate it worked