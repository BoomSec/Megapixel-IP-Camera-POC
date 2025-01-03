# Megapixel IP Cam Exploit POC

This Python script is a proof of concept for exploiting default credentials in Megapixel IP Cameras. 
The code attempts to change a visual setting on the security camera by sending a network request using a provided list of IP addresses and ports and default credentials.

For those curious about it. The Cameras host a webui with password authentication to make changes.
By reviewing the incoming and outgoing network/web requests using a tool like burp. You will see that the username and password are sent in the requests.

If you want to know what these default credentials are. I challenge you to take apart the code and see how it works, the credentials are there in the code......

---

_If you don't want your time wasted the credentials that come default with mode of these models are listed below_

```bash
admin
```

_with no password (just leave that prompt blank)_

---

## Usage

1. First, ensure you have Python installed on your system.
2. Clone the repository to your local machine using the following command:

```bash
git clone https://github.com/BoomSec/Megapixel-IP-Camera-POC.git
```

3. Navigate to the cloned directory:

```bash
cd Megapixel-IP-Camera-POC
```

4. Find and confirm the IP address and Port of the camera's UI:
_you can find examples of these on shodan by searching for the following_
```bash
'WWW-Authenticate: Basic realm="Megapixel_IP_Camera"'
```

5. Put together your list:
_From here you can make note of the ip address and port of the hosted web interface_
_Then you can add it to a text file using the formatting 'ipv4:port' I have listed some examples below_

```bash
1.1.1.1:11
8.8.8.8:88
69.69.69.69:420 *heheheh nice*
```
_After making your list dont forget to save the progress on the text file_
_Also be sure to make a note of the text file name so you don't forget it. We are going to need this later_


5. Run the script:
_Now the moment we have been all waiting for H4CkerMan Time™_
_Time to run the script. You can do this by calling the script with the name of your text file containing the ip address/addresses_

```bash
python CameraExploit.py TargetCameras.txt
```

## Note for Users Finding a Repository URL Displayed on Their Cameras

If you have discovered a repository URL displayed on your camera, it is possible that your camera may be vulnerable. This could be due to default credentials being used or other security vulnerabilities.

### What to Do If You Suspect Your Camera May Be Vulnerable

If you have found this repository from a link displayed on your camera and are concerned about the security of your device, we advise the following steps:

1. **Immediate Action**:
   - Disconnect the camera from the network to prevent unauthorized access.
   - If possible, change the default credentials or passwords associated with the camera.

2 **Review the Documentation**:
   - Refer to the user manual or documentation for your camera model to find instructions on securing and updating its settings.

3. **Contact the Manufacturer**:
   - Reach out to the manufacturer or vendor of the camera for guidance on securing your device and addressing potential vulnerabilities.

4. **Stay Informed**:
   - Regularly check for firmware updates and security advisories for your camera model.

### Important Note

It is crucial to ensure the security of your devices, especially those with network connectivity. We strongly emphasize the importance of securing your devices to prevent unauthorized access and unauthorized use.

If you have any concerns or questions, please seek guidance from qualified professionals or security experts.

## Web Interface

The web interface designed for the Megapixel IP Camera is in response to McBazza's suggestion in Issue #1 

## Hosting Limitation

Please note that due to the web page making requests to HTTP addresses while being hosted on a HTTPS site, hosting the web interface on github.io has resulted in a multitude of errors. As a result, I am currently unable to host the page on github.io so you will unfortunately have to byo hosting system.

_For me I have tested and put the files on a Raspberry Pi I have that is hosting pi-hole at the moment, so if you have one handy its a perfect candidate to host locally :D_


## Disclaimer

This script is intended for educational and proof of concept purposes only. It is crucial to emphasize that accessing security cameras without proper authorization is illegal and unethical. The use of this code to exploit security cameras that do not belong to you is strictly prohibited and may result in legal consequences.

By using this code, you agree that you will only use it in controlled environments, such as on devices and security cameras that you own or have explicit permission to test.

The author of this script is not responsible for any misuse or unlawful use of this code.


