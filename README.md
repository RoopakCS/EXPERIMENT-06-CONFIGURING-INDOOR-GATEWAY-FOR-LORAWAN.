# EXPERIMENT-06-CONFIGURING-INDOOR-GATEWAY-FOR-LORAWAN

## Aim:

To configure Dragino LPS8 Indoor LoRaWAN gateway for things network .

## Components required:

Dragino LPS8 Indoor LoRaWAN gateway, ETHERNET cable RJ45,Internet connection

## Theory :

Dragino LPS8 Indoor LoRaWAN gateway

![image](https://github.com/user-attachments/assets/820683bd-7548-4cb2-811c-d5aca77b09cc)

The LPS8 is an open-source LoRaWAN Gateway. It lets you bridge LoRa wireless network to an IP network via WiFi, Ethernet. The LoRa wireless allows users to send data and reach extremely long ranges at low data rates. The LPS8 uses a Semtech packet forwarder and is fully compatible with the LoRaWAN protocol.

![image](https://github.com/user-attachments/assets/6c7e5885-67e4-4dd2-82bc-3ea2c9514a8a)

It includes an SX1308 LoRa concentrator, which provides 10 programmable parallel demodulation paths. LPS8 has pre-configured standard LoRaWAN frequency bands to use for different countries. Users can also customize the frequency bands to use in their own LoRa network.
The gateway has an antenna to receive the LoRa Packets in 8-channels. On the front side, it has a USB Type C port for Input Power of DC 5V,2A. Apart from the power, it also has an Ethernet port, USB Host Port & a Toggle button to reset the gateway.

![image](https://github.com/user-attachments/assets/95a5bd41-2219-4c45-8862-e961ebc33fb3)

At bottom of the gateway, it has the LoRa Pico Station information Like Model-LPS8, Frequency Band, Serial Number, and the WiFi mac address.

LED Indicators
![image](https://github.com/user-attachments/assets/e955113c-84af-4095-bfa2-4386a9cd43e8)

LPS8 has totally four LEDs, They are:
➢ Power LED: This RED LED will be solid if the device is properly powered.
➢ LoRa LED: This RGB LED will blink GREEN when the LoRaWAN module starts or transmit a
packet.
➢ SYS LED: This RGB LED will show different colors in the different states:
✓ SOLID BLUE: The device is alive with a LoRaWAN server connection.
✓ BLINKING BLUE: a) Device has internet connection but no LoRaWAN Connection. or b)
The device is in the booting stage, in this stage, it will BLINKING BLUE for several seconds and
then with SOLID RED and BLINKING BLUE together
✓ SOLID RED: The device doesn’t have an Internet connection.
➢ ETH LED: This LED shows the ETH interface connection status.

## Procedure :

The LPS8 is configured as a WiFi Access Point by factory default. You can access and configure the LPS8 after connecting to its WiFi network, or via its WAN Ethernet port.

1. Connect via WiFi

![image](https://github.com/user-attachments/assets/ef24dd5e-7283-491b-a5b9-06803d8d62d9)

2. At the first boot of LPS8, it will auto-generate a WiFi network called dragino-xxxxxx with password: dragino+dragino
   You can use a PC to connect to this WiFi network. The PC will get an IP address of 10.130.1.xxx and the LPS8 has the default IP 10.130.1.1.

3. Connect via Ethernet with DHCP IP from router

![image](https://github.com/user-attachments/assets/d9d974cc-18fa-4628-9596-ba55cd263e18)

Alternatively, connect the LPS8 Ethernet port to your router and LPS8 can obtain an IP address from your router. In the router’s management portal, you should be able to find what IP address the router has assigned to the LPS8. You can also use this IP to connect.

4.  Connect via WiFi with DHCP IP from router

![image](https://github.com/user-attachments/assets/f80ab109-d131-4787-a06c-c8091e5674b2)

5. Configuring Network Connection to Gateway
   You can use any of the methods mentioned above to connect the Gateway to WiFi Network. The LPS8 is configured as a WiFi Access Point by factory default. So I followed the first method to connect to the network.

The Gateway will generate WiFi access point called dragino-xxxxxx with password: dragino+dragino. Connect to that Access point by entering the password.

6.After successful connection, open any of the Web Browser. Then browse to the following IP: 10.130.1.1. A web page like the below will appear.

![image](https://github.com/user-attachments/assets/789bb829-ed3e-411d-b755-fd7ae281ecbb)

Enter the User Name: root & Password: dragino. Then hit enter. A webpage like below will appear.

![image](https://github.com/user-attachments/assets/db651005-f08f-4c93-a9d3-76a01811c4b0)

7.The login page will show internet connectivity status. If it is connected to the internet, it is wifi or ethernet. The webpage will also show the status of LoRaWAN connection, the LoRa connection, and the Access point connection.At this moment the Dragino LPS8 LoRaWAN Indoor Gateway doesn’t have an internet connection. So, first, we need to configure the LPS8 as a WiFi client by providing the Wifi credentials.

8.Go to the network, then click on WiFi.

![image](https://github.com/user-attachments/assets/413e2e88-8a17-455b-a5c5-6cb6ded5ff76)

9.The following Webpage will appear.

![image](https://github.com/user-attachments/assets/cfcd705b-1c0a-4012-a1ca-0d841557eda8)

10. Click on the WiFi survey and select your WiFi Network. Then enter the WiFi password. Also “Enable WiFi client” option. Finally, you can click on save and apply.

![image](https://github.com/user-attachments/assets/058fbf83-1888-4e30-88e6-3c56b17f2732)

11.Now you will get the following response as green. Congratulations, your Gateway is connected to the WiFi Network.

![image](https://github.com/user-attachments/assets/3ac3559b-1fbc-4f0b-adf9-bd31c071bcab)

Now uncheck the above Enable WiFi access point option and click on the save and apply button. This will disable the Access Point. At this time you need to find the IP Address of your Gateway. You can get the IP Address from your WiFi Router Login page.

12. Configuring Gateway Frequency & Gateway IDNow, we need to setup the LoRa frequency. To do that go to the LoRa option as shown in the image below.

![image](https://github.com/user-attachments/assets/d2cb1f19-0c43-4a57-a06f-d6e78029e4ef)

14. From the frequency option you need to select your LoRa frequency. Currently, I am using my LoRa devices from INDIA. So I choose IN865 which is basically between (865–867 MHz)
15. You can select the frequency band allowed in your region. There is also an option for GPS Enabling which you may enable or disable. Finally, click on save and apply.
    The frequency band is allocated now. Now we need to get the Gateway ID. To get that go to the following option as LoRaWAN Semtech UDP.

16.Copy the Gateway ID as this will be required later. Then select the LoRaWAN Server as The Things Network . Select the server address https://iot.saveetha.in

![image](https://github.com/user-attachments/assets/540c1f70-d212-4ee4-b757-357ce45946c1)

17.Click on save & apply. So finally the setting up of LPS8 Dragino LoRaWAN Gateway completes.

## OUTPUT

![IMG_20250514_113651](https://github.com/user-attachments/assets/734b3f62-116b-473e-ae6b-23fb1dac68d5)
![Screenshot 2025-05-14 112620](https://github.com/user-attachments/assets/a64fce98-653e-462a-8e93-2ae14fd7f478)

## Result:

The Dragino LPS8 Indoor LoRaWAN Gateway was successfully configured and connected.
