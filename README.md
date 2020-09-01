# Getting Started with Raspberry Pi


Do you want to get started with Raspberry Pi? This is a right place to be.

# Pi 101


<details> 
  <summary>What is Raspberry Pi? </summary>
  Raspberry Pi is credit-card sized computer system.

  </table>
</details>

<details> 
  <summary>What are the components of Raspiberry Pi 3 Model B? </summary>
  
  Its components are listed below:<br>
  - USB Port x4<br>
  - LAN port<br>
  - In-built WiFi Modubr<br>
  - Display Port<br>
  - HDMI Port for Video Output<br>
  - Charging Port<br>
  - Memory Card<br>
  - Audio & Video Jack<br>
  - MicroSD Slot<br>
  - On-board Bluetooth 4.1 WiFI<br>
  GPIO Pins<br>
  ![My Image](https://github.com/collabnix/raspberrypi/blob/master/images/IMG_20200829_124256.jpg)
  </table>
  
</details>

<details> 
  <summary>How to connect Raspberry Pi to a Monitor? </summary>
  Using HDMI cable
  
![My Image](https://github.com/collabnix/raspberrypi/blob/master/images/IMG_20200829_125708.jpg)


  </table>
</details>


<details> 
  <summary>Which OS does Raspberry Pi run? </summary>
  Raspbian OS

  </table>
</details>

<details> 
  <summary>How to setup a static IP on Raspberry Pi?</summary>


* Open DHCP config for editing

```sh
sudo vim /etc/dhcpcd.conf
```

* Add your network interface at the top (run `route -n` to check yours)


```sh
# eth0 or whatever interface you use
interface wlan0

# This will always be your IP when you connect to this gateway
static ip_address=192.168.1.99

# Default gateway IP
static routers=192.168.1.1

# Space separated list of DNS servers
# The ones added here are Cloudflare servers
static domain_name_servers=1.1.1.1 1.0.0.1
```

* Save and reboot!

  </table>
</details>


<details> 
  <summary>How to access Raspberry Pi from an external network?</summary>
  You need to go into your router settings and set up port forwarding to the static IP of your raspberry pi, which you can get by running the following command:
  `hostname -I`

If you want to ssh into your rpi from external network then use the static IP and port 22, if any other service then use the same IP with the port of your choice.

  </table>
</details>



<details> 
  <summary>How to setup SSH in raspberry Pi</summary>

* Run the following command and enable ssh:

```sh
sudo raspi-config
```

* Get your local IP

```sh
hostname -I

# or
ip addr | grep 192.168
```

* You can now SSH!

---

## Setting up SSH keys

* Go to raspberry PI and generate the SSH key pair (id_rsa and id_rsa.pub)

```sh
ssh-keygen -t rsa
```

* Add the key in known_hosts

```sh
cat id_rsa.pub >> ~/.ssh/known_hosts
```

* Do not keep the private key on the rpi for safety concerns. Copy it over to the client machine. To connect, run:

```sh
ssh -i id_rsa pi@<ip-addr-of-pi>
```
  </table>
</details>
