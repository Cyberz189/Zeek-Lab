# Zeek Lab

## Objective


The objective of utilizing Zeek is to enhance network security by providing comprehensive visibility into network traffic, enabling rapid detection of known and emerging threats through signature-based and protocol analysis techniques, and empowering security teams to develop and deploy custom detection rules tailored to their organization's specific security needs.

### Skills Learned


- Zeek offers real-time network visibility, aiding security teams in monitoring and understanding network activity.
- It uses signature-based detection to swiftly identify known threats by comparing network traffic against a database of predefined signatures.
- Through protocol analysis at the packet level, Zeek detects anomalies and suspicious behavior, enhancing its ability to identify sophisticated threats.
- Its flexible scripting language enables the creation of custom detection rules, empowering security professionals to detect and mitigate various threats effectively.

### Tools Used

- Zeek
- Linux
- Terminal

  
## Steps

![IMG_8660](https://github.com/Cyberz189/Zeek-Lab/assets/163569052/f6e9a99e-4582-400c-9128-89a659bd42e1)
![IMG_8661](https://github.com/Cyberz189/Zeek-Lab/assets/163569052/93d07833-6eaf-4512-9f6b-e0ee44cea9a3)


To start off, first find the folder with the signatures file, used to edit and set the "rules" of what Zeek is goinhg to look for once activated. 

![IMG_8662](https://github.com/Cyberz189/Zeek-Lab/assets/163569052/30fb87c2-9c6f-44bf-a4b4-9b4b41fd6118)
![IMG_8663](https://github.com/Cyberz189/Zeek-Lab/assets/163569052/361c5761-1457-43de-a9e7-9dd18ba57cf5)


Opening the signature file allows me to edit the IP Protocol (TCP, Layer 4), which is identified as ip.proto == tcp, and the destination port, which in this case is port 80. The payload enables us to define the type of content we are searching for in the packets, in this case, "password". The event allows us to configure the alert once the signature has been confirmed.


![IMG_8664](https://github.com/Cyberz189/Zeek-Lab/assets/163569052/2a5d1ab6-06f6-4a1c-b76e-16ba330f3e2d)

Now, by running Zeek and identifying the pcap file I would like to check (http.pcap) and the signature (http.password-sig), I can receive logs generated by Zeek's signatures to further inspect the packet data within the pcap file. The command "-C" is used to ignore checksums, "-r" is used to "read" the pcap file, while "-s" specifies what kind of signature file is being used. The complete command is as follows: "zeek -C -r http.pcap -s http-password.sig". The generated logs from the command include conn.log, files.log, http.log, notice.log, packet_filter.log, and finally signatures.log.


![IMG_8665](https://github.com/Cyberz189/Zeek-Lab/assets/163569052/8c7cb79c-a007-48dc-b6f0-a86cf2f96abc)
![IMG_8666](https://github.com/Cyberz189/Zeek-Lab/assets/163569052/ba955d04-d359-4c8c-be77-2b933d9e3a46)



Using the "cat" command to open the signature.log gives us details on what zeek picked up. Among the numerous information detected by the zeek signature is the source address, source port, destination address, and destination port.




Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
