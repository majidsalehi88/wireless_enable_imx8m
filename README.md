# wireless_enable_imx8m

1. Use ifconfig to bring interface up:

   ifconfig wlan0 up

2. Use editor to edit /etc/wpa_supplicant.conf :

   mcedit /etc/wpa_supplicant.conf

3. Change the Network block to as follows (keep the quotation marks):

   Network={
      scan_ssid=1
      ssid="YOUR_SSID_NAME"
      psk="YOUR_PASSWORD"
   }
note : save editor Esc >>>> :x
 

4. Associate the wlan with config:
   wpa_supplicant -B -i wlan0 -c /etc/wpa_supplicant.conf

 

5. Check if you wlan is up:

   ifconfig wlan0

 

6. Rung DHCP client from BusyBox to get the IP (yup, there is no dhclient):
   udhcpc -i wlan0

 

7. Check the network:
   ping 8.8.8.8
