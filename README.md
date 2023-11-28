# Megapixel IP Camera Default Credentials Exploitation Proof of Concept

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

_See my first attempt below. Where I run the code and point it at my list of <del>victims</del> I mean personally owned network based security cameras. That you have explicit access or permission to use_

```bash
python CameraExploit.py TargetCameras.txt
```

## Disclaimer

This script is intended for educational and proof of concept purposes only. It is crucial to emphasize that accessing security cameras without proper authorization is illegal and unethical. The use of this code to exploit security cameras that do not belong to you is strictly prohibited and may result in legal consequences.

By using this code, you agree that you will only use it in controlled environments, such as on devices and security cameras that you own or have explicit permission to test.

The author of this script is not responsible for any misuse or unlawful use of this code.

---