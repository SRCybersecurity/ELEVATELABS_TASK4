# ELEVATELABS_TASK4  
***Configure and test firewall rules in windows and Linux.*** <br></br>



</br>Objective: Configure and test basic firewall rules to allow or block traffic.
</br>Tools: Windows Firewall / UFW (Uncomplicated Firewall) on Linux.
</br>Deliverables: Screenshot/configuration file showing firewall rules applied.
<br></br>

Here's a step-by-step guide to configure and test firewall rules on both Windows and Linux (UFW), depending on your system. Choose the section that matches your OS. <br></br>

***FOR LINUX (UFW - Uncomplicated Firewall)*** <br>

</br>Make sure UFW is installed and enabled:
</br>Run cmd
</br>sudo apt install ufw
</br>sudo ufw enable <br></br>

***1. Open Firewall Configuration Tool*** <br>
</br>UFW is used via the terminal. No GUI needed. <br></br>

***2. List Current Firewall Rules***  <br>
</br>Rum cmd
</br>sudo ufw status numbered  <br></br>

***3. Add Rule to Block Inbound Traffic on Port 23 (Telnet)***  <br>
</br>Run cmd
</br>sudo ufw deny 23    <br></br>

***4. Test the Rule***  <br>
</br>You can test with:
</br>•	Telnet client:
</br>Run cmd
</br>telnet localhost 23
</br>•	Or use nc (netcat):
</br>Run cmd
</br>nc -zv localhost 23
</br>You should see a connection refused or timeout.  <br></br>

***5. Add Rule to Allow SSH (Port 22)***     <br>
</br>Run cmd
</br>sudo ufw allow 22
</br>This is important if you're using SSH to manage the system remotely.  <br></br>

***6. Remove the Block Rule (Restore Original State)***  <br>
</br>Rum cmd
</br>sudo ufw delete deny 23
</br>Use sudo ufw status numbered to find the rule number if needed. <br></br>

***7. Following documented Commands***  <br>
</br>1. Run cmd
</br>2. sudo apt install ufw
</br>3. sudo ufw enable
</br>4. sudo ufw status numbered
</br>5. sudo ufw deny 23
</br>6. telnet localhost 23
</br>7. sudo ufw allow 22
</br>7. sudo ufw delete deny 23 <br></br>




***FOR WINDOWS (Windows Defender Firewall)*** <br>

***1. Open Firewall Configuration Tool***  <br>
</br>•	Go to Control Panel > System and Security > Windows Defender Firewall.
</br>•	Or search: "Windows Defender Firewall with Advanced Security". <br></br>

***2. List Current Firewall Rules***  <br>
</br>•	In the Advanced Settings panel, check:
</br></br>o	Inbound Rules
</br></br>o	Outbound Rules       <br></br>

***3. Block Inbound Traffic on Port 23***    <br>
</br>•	In Inbound Rules, click New Rule...
</br>•	Select Port > Click Next
</br>•	Choose TCP > Specific local ports: 23
</br>•	Action: Block the connection
</br>•	Apply to all profiles (Domain, Private, Public)
</br>•	Name it: Block Telnet Port 23    <br></br>

***4. Test the Rule***    <br>
</br>Use Telnet client:
</br>1.	Install from Optional Features if not present.
</br>2.	Run cmd
</br>telnet localhost 23
</br>You should get a failure to connect.   <br></br>

***5. Allow SSH (Port 22) (Optional for Windows)***  <br>
</br>Not typically used unless you're running OpenSSH server. If so:
</br>•	Go to Inbound Rules > New Rule...
</br>•	Port: 22 > Allow the connection    <br></br>

***6. Remove the Test Rule***  <br>
</br>•	Go to Inbound Rules
</br>•	Find Block Telnet Port 23, right-click > Delete   <br></br>

***7.Following documented Steps***  <br>
</br>1.	Control Panel > Firewall > Advanced Settings
</br>2.	Inbound Rules > New Rule > Block TCP port 23
</br>3.	Telnet test
</br>4.	Allow rule for port 22 (optional)
</br>5.	Delete the test rule     <br></br>

***8. Summary: How Firewall Filters Traffic*** <br>
***Firewall in Linux***   <br>
</br>Firewalls monitor and control incoming and outgoing network traffic based on predefined rules. They:
</br>•	Allow or deny packets based on IP address, port, or protocol.
</br>•	Protect systems from unauthorized access.
</br>•	Act as a barrier between trusted and untrusted networks.     <br></br>

***Firewall in Windows***  <br>
</br>Windows Firewall filters traffic using rules based on:
</br>•	Port numbers
</br>•	Application names
</br>•	Network profiles
</br>It ensures that only authorized traffic can reach or leave your device, improving security.   <br></br> <br></br>


***THANK YOU*** <br></br> <br></br>

***END*** 

Outcome: Basic firewall management skills and understanding of network traffic filtering.

