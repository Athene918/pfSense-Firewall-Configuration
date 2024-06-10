# pfSense-Firewall-Configuration

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*xIq1OJn986w6ze2imST9Jw.png)

## pfSense General Configuration
### Web Portal Setup
On the Kali Linux VM, open the web browser and navigate to **https://10.0.0.1**.

You will get the following message Warning: Potential Security Risk Ahead. This warning can be ignored. We get this warning because the URL that we are trying to access does not use the secure HTTP (HTTPS). Click on **Advanced** and then click on **Accept the Risk and Continue.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*MG3BD0QnSq2eg2aL.png)

This will open the pfSense Web UI login page. Login using the default credentials.
Username: **admin**
Password: **pfsense**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*r0G3T_43qxCKG3BD.png)

Click on **Next**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*si4phqToy0smVJg1.png)

Click **Next** again.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*MPdKQphSbMWYTEgI.png)

In the **General Information** section. Provide a Hostname and Domain name. This can be any name you choose. The hostname can be used to identify the pfSense VM on the network. Uncheck the Override DNS option and then click **Next**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*pG8UpSw1kPad7G86.png)

Select your Timezone and then click **Next**.

Scroll to the bottom of the page and look for the RFC1918 Networks section. Uncheck the **Block RFC1918** Private Networks option.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*Xx04UMmY3BwkNPZs.png)

> We disable this option because our WAN interface is not an real WAN interface. It uses an private IP address instead of an public IP address which would be used by a real WAN interface to connect to the Internet.
> Our WAN interface uses a private IP address to send data packets to the host system which then sends the data packets to the router present in the network.

Don’t change any value on this page. Click on **Next**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*6VUSJ89zuvP17Grj.png)

Enter a new password for the admin user. Store the password in a secure place.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*MQ9FnvohrFmMTJ9_.png)

Click on **Reload** to apply the changes.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*1heEA7tM5T1GyBip.png)

Click on **Finish**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*7jX24M9CLfz72G3x.png)

Once the onboarding is complete we will be able to access the pfSense dashboard.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*osjiCJPq7XoC2M6i.png)

### Interface Renaming
From the navigation bar select **Interfaces -> OPT1**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*Sb_O4AvK5YRBTKo9.png)

In the Description field enter **CYBER_RANGE**. Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*pURc-7ZJ9q909pYZ.png)

At the top of the page, a new popup will appear. Click on **Apply Changes**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*8JZPgvIPs8sm7Jhv.png)

From the navigation bar select **Interfaces -> OPT2**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*eDjLWHUprt-Xp58a.png)

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*eDjLWHUprt-Xp58a.png)

In the Description field enter **AD_LAB**. Scroll to the bottom of the page and click on **Save**. A popup will appear at the top of the page click on **Apply Changes**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*qWU4NmxILUzFPofJ.png)

### DNS Resolver Configuration
From the navigation bar select **Services -> DNS Resolver**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*gjHKv4dxvi4PWZNE.png)

Scroll to the bottom of the page, look for the highlighted options and enable them. No need to save just yet. Scroll to the top of the page.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*xfWjxhDoTUCQfDGS.png)

Click on **Advanced Settings**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*jhNpvaM0Q1Hg25zs.png)

Scroll down to the **Advanced Resolver Options** section and enable the highlighted options. Scroll to the end and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*zXjRFiDZhcvBDPMu.png)

A popup will appear at the top of the page. Click on **Apply Changes**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*E-DOWQ6J9p8XOCAf.png)

### Advanced Configuration
From the navigation bar select **System -> Advanced**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*O9cRU8aELfxCL8Rk.png)

Go to the **Networking tab**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*igo0TqEgsWoefoBp.png)

Scroll to the end in the **Network Interfaces** section and enable the highlighted option. This option should improve the performance of pfSense. Click on **Save**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*vaUoktm2rnfjp1K7.png)

A popup will appear click on **OK** to reboot pfSense.

![image](The following page will be shown while pfSense applies the changes.)

The following page will be shown while pfSense applies the changes.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*w-2YW1DlOSWCmH6M.png)

Once the reboot is complete we will be asked to log in again. Use the new password to access the Dashboard.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*eJ5CHGgvTij7MWUj.png)

## Kali Linux Static IP Assignment
From the navigation bar select **Status -> DHCP Leases**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*tuaaCnNT7jjlOa32.png)

In the **Leases** section, we should see the Kali Linux VM with its current IP address. Click on the highlighted + icon to assign a static IP to Kali Linux. The static IP will make it easier for us to apply firewall rules to interfaces that should only be able to reach the Kali VM.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*IOUfantl7FqXZZSZ.png)

In the IP Address input enter **10.0.0.2**. Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*bpwZckldtulOCewn.png)

A popup will show up at the top of the page. Click on **Apply Changes**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*jrsNIi2ANRKdp5ek.png)

### Refresh Kali Linux IP Address
Open a terminal on the VM. Use the following command to see the current IP address.

````bash
ip a l eth0
````
We want the VM to release the current IP address and use the static IP that was reserved. This can be achieved using the following command:

````bash
sudo ip l set eth0 down && sudo ip l set eth0 up
````

Enter password when prompted. To confirm that the VM is using the static IP run the following command:

````bash
ip a l eth0
````

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*oNAoRxQlvtY976jf.png)

### pfSense Firewall Configuration
From the navigation bar select **Firewall -> Rules**.

![images](https://miro.medium.com/v2/resize:fit:720/format:webp/0*iz1glshX0wT6HoIV.png)

### LAN Rules
Go to the **LAN** tab. The LAN tab will have some predefined rules.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*fI4U5BwNvR9qLofG.png)

Click on the “Add rule to top” button to create a new rule.

![image](https://miro.medium.com/v2/resize:fit:640/format:webp/0*-42iYTyBLIeA4NO1.png)

Change the following options:
Action: **Block**
Address Family: **Ipv4+IPv6**
Protocol: **Any**
Source: **LAN subnets**
Destination: **WAN subnets**
Description: **Block access to services on WAN interface**

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*s0glugNlHYseNol0.png)

The final LAN rules should look as follows.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*2ZGmav5KxY25FrHM.png)

The order of the rules is important. If the order is not correct. Drag the rules around till it matches the above image.

## CYBER_RANGE Rules
Before creating the rules for **CYBER_RANGE** we need to create a Alias. From the navigation bar select **Firewall -> Aliases**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*h_q7aGHNfj2otEMq.png)

In the IP tab click on **Add** to create a new alias.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*raLolXS7k1fqbGDn.png)

Enter the following details:
Name: **RFC1918**
Description: **Private IPv4 Address Space**
Type: **Network(s)**
Network 1: **10.0.0.0/8**
Network 2: **172.16.0.0/12**
Network 3: **192.168.0.0/16**
Network 4: **169.254.0.0/16**
Network 5: **127.0.0.0/8**

Click on **Save** to create an alias.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*Sz_e9hbg44O0yrDH.png)

A popup will show up at the top click on **Apply Changes**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*Bjld4n8U22JDrJ6Z.png)

The final result should be as follows:

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*aZE6M2VlrUqF8PcA.png)

From the navigation bar select **Firewall -> Rules**. Select the **CYBER_RANGE** tab.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*IjVwcp00ucDrp5Qq.png)

Use the “Add rule to end” button for all the rules.

![image](https://miro.medium.com/v2/resize:fit:640/format:webp/0*dXIfCRUl8HCqzr5X.png)

Configure the rule as follows: Address Family: **IPv4+IPv6**
Protocol: **Any**
Source: **CYBER_RANGE subnets**
Destination: **CYBER_RANGE address**
Description: **Allow traffic to all devices on the CYBER_RANGE network**

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*pNVJ3_tkvmBgbZwX.png)

A popup will appear at the top to save the changes, no need to click on that just yet. Click on the “Add rule to end” button to create a new rule.

The rule has the following details:
Protocol: **Any**
Source: **CYBER_RANGE subnets**
Destination: **Address or Alias - 10.0.0.2**
Description: **Allow traffic to Kali Linux VM**

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*vXBnR5DHhLzRKJBb.png)

Click on the “Add rule to end” button to create a new rule.

Create a rule with the following settings:
Protocol: **Any**
Source: ***CYBER_RANGE subnets**
Destination: **Address or Alias - RFC1918 (Select Invert match)**
Description: **Allow to any non-private IPv4 Address*

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*kKz5-pz-DWd3tOza.png)

Click on the “Add rule to end” button to create a new rule.

Create a rule with the following settings:
Action: **Block**
Address Family: **IPv4+IPv6**
Protocol: **Any**
Source: **CYBER_RANGE subnets**
Description: **Block access to everything**

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*EpqfYS57Kdsrc3Fq.png)

Click on the **Apply Changes** button in the popup at the top of the screen.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*i7LTFn8hMvVwp4_m.png)

The final rules should look as follows:

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*nJWXL_usJo0N-Dv1.png)

## AD_LAB Rules
Click on the **AD_LAB** tab. Use the “Add rule to end” button to create new rules.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*qrbiTHSv9zLwwtDs.png)

Create a rule with the following settings:
Action: **Block**
Address Family: **IPv4+IPv6**
Protocol: **Any**
Source: **AD_LAB subnets**
Destination: **WAN subnets**
Description: **Block access to services on WAN interface**

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*XFeYHi4Z31-LUFvj.png)

A popup will appear at the top to save the changes, no need to click on that just yet. Click on the “Add rule to end” button to create a new rule.

The rule has the following details:
Action: ***Block**
Address Family: **IPv4+IPv6***
Protocol: **Any**
Source: **AD_LAB subnets**
Destination: **CYBER_RANGE subnets**
Description: **Block traffic to CYBER_RANGE interface**

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*UJk5Pg5UJmScW7sq.png)

Click on the “Add rule to end” button to create a new rule.

The rule has the following details:
Address Family: **IPv4+IPv6**
Protocol: **Any**
Source: **AD_LAB subnets**
Description: **Allow traffic to all other subnets and Internet**

Scroll to the bottom and click on **Save**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*RHN0PAfThO6SFPVu.png)

Click on the **Apply Changes** button in the popup at the top of the screen.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*WzKAyy2_R4MNbjji.png)

The final rules should look as follows:

![images](https://miro.medium.com/v2/resize:fit:720/format:webp/0*YiGM3yLpq17YdlSC.png)

### pfSense Reboot
Now we need to restart pfSense to persist the firewall rules. From the navigation bar select **Diagnostics -> Reboot**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*SFhMCCtADg1pgYlK.png)

Click on **Submit**.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/0*abWavM3ClSsEJu4J.png)



