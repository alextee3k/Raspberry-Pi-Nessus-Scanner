# Raspberry-Pi-Nessus-Scanner

Completed this project by installing a headless Linux OS onto the Raspberry Pi and enabling SSH authentication. Once able to take control of the Pi remotely, install Nessus Vulnerability Scanning software using the following curl command: 

**curl --request GET \
  --url 'https://www.tenable.com/downloads/api/v2/pages/nessus/files/Nessus-10.7.1-raspberrypios_armhf.deb' \
  --output 'Nessus-10.7.1-raspberrypios_armhf.deb'**

Once the download is complete, ls and you should see a .zip file. dpkg it using:

**sudo dpkg -i Nessus-10.7.1-raspberrypios_armhf.deb**

Once the install has passed, you must now start the nessus process, then check that it is in fact running. You can do this by running the following commands

**systemctl start nessusd.service** # this will start the service, authenticate using credentials.

When authentication completes, run: 

**systemctl status nessusd.service** # this will ensure that the service is running. 

Make sure there are no errors and that your OS instruction set matches Nessus instruction set (32-bit, 32-bit). (errors occured when downloading 64-bit headless Raspberry Pi OS and downloading 32-bit Nessus Software, reformatted Pi with 32-bit OS and error no longer occured)

Once you ensure that the service is running, go to your browser and enter, https://*raspberrypiIP*:8834 

If entered properly, you will be taken to the Nessus web interface that is being hosted from your RSPi. Allow the configuration process to take place, sign up for your account using Nessus Essentials as this will give you a limited amount of free scans for later use. 

Ensure all the necessary policies and software updates take place as needed. 
