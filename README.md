# Google-Cybersecurity-Linux-Distribution
This Python script automates several package management tasks on a Linux system using APT (Advanced Package Tool). 
import subprocess

def run_command(command):
    try:
        result = subprocess.run(command, shell=True, check=True, text=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE)
        return result.stdout
    except subprocess.CalledProcessError as e:
        return e.stderr

# Confirm APT is installed
print("Checking if APT is installed...")
print(run_command("apt --version"))

# Install Suricata
print("Installing Suricata...")
print(run_command("sudo apt install -y suricata"))

# Confirm Suricata installation
print("Confirming Suricata installation...")
print(run_command("suricata --version"))

# Uninstall Suricata
print("Uninstalling Suricata...")
print(run_command("sudo apt remove -y suricata"))

# Confirm Suricata uninstalled
print("Confirming Suricata is uninstalled...")
print(run_command("which suricata"))

# Install tcpdump
print("Installing tcpdump...")
print(run_command("sudo apt install -y tcpdump"))

# List installed applications
print("Listing installed applications...")
print(run_command("apt list --installed"))

# Reinstall Suricata
print("Reinstalling Suricata...")
print(run_command("sudo apt install -y suricata"))

# Confirm both applications are installed
print("Confirming Suricata and tcpdump installation...")
print(run_command("suricata --version"))
print(run_command("tcpdump --version"))
