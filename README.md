How frustrating is it to type a password on a computer where you haven't set up your favorite password manager? Quite annoying, isn't it?

## Well, allow me to introduce ✨PassRF✨

PassRF serves as a bridge between your smartphone's password manager and the target computer.

It functions by creating an access point with a small HTTP server. This server includes a field where you can paste the password you want PassRF to input.

## The current features of PassRF include:

- WPA2-PSK AES
- An easy-to-use first-run wizard.
- Automatic random password generation upon initial setup. You get a 32-character password with symbols, numbers, and more.
- Only one client is allowed to be connected to the access point, ensuring the sent password can't be intercepted.

## Here are the steps to get it up and running:

1. Assemble the hardware:<br>![PassRF_bb](https://github.com/gvrubio/PassRF-Arduino/assets/82053814/2053106f-7483-4206-81bc-debceb164943)
2. Flash the devices. Your should use "Arduino Leonardo" for the arduino, and "Wemos D1 Mini" for the ESP8266.
3. Connect to the "SETUP" access point.
4. Go to 192.168.4.1 in your browser.
5. Copy the WPA password.
6. Click "SAVE PASSWORD!"
7. A new network named AP-XXXXXX (<- Randomly Generated Name) should become visible. This is still WIP.
8. Connect to it using the password you copied earlier.
9. Access 192.168.4.1 in your browser again. Now, you should see the password input field.

## What's the hardware needed?
The hardware is dirt cheap and should be easy to buy and build.

- A Wemos D1 Mini ESP8266, around 3 or 4€.
- An arduino pro micro, also around 3 or 4€.
- A TXE108E 3.3v to 5v bidirectional voltage level converter, you would not believe it, it's around 3 or 4€ as well!!!! 😲.
- Soldering skills, wire. You could even use some of those arduino bridge wires, and no soldering is required.
- I have an initial design for a PCB, it is my first time working with Kicad, so expect some bullshit from it, you are free to take it and modify it.

Here is how the PCB looks:
![PassRF](https://github.com/gvrubio/PassRF-Arduino/assets/82053814/751e838e-2f41-40b8-b52c-9649d4af47c7)

And here is the upload:

## What are some features expected on the future:
- Reset button to restart the WPA password wizard.
- Automatic password reset on different client connection.
- Client whitelist.
- Android Keepass2Android integration plugin.
- Serial CRC32 checksum and json data over serial.
- Better Web UI, now it just works 😅

## Which things could make it even more secure:

- SSL between the smartphone and the web server. <- This hasn't been implemented because it would significantly complicate the setup process. I'm open to hearing other ideas.
- Metalic case to avoid the serial signal to be catched over the air. Help us Faraday. <- Use some altoids or any other metallic case, solder a wire to the case and put it to the device ground.
- Encryption on the serial communication. <- AES on an 8-bit arduino? Maybe xD. I hear ideas as well.
