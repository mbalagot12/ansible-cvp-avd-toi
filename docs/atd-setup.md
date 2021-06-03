# TOI Lab preparation using Arista Test Drive

Connect to ATD Jump box using web interface. For more information ask to your local SE.

## Clone the Git repo

```shell
# Clone the Git repo on the ATD jumphost
$ git clone https://github.com/arista-netdevops-community/ansible-cvp-avd-toi.git

Move to repository folder
$ cd ansible-cvp-avd-toi
```

## Install Virtual Environment

Run TOI in a python's virtual environment:

```shell
# Upgrade pip if needed. This 
$ /usr/local/bin/python -m pip install --upgrade pip

# Install virtualenv if not part of your system
$ python -m pip install virtualenv

# Add the path
$ export PATH=/usr/local/bin:/usr/bin:/bin:/usr/games:/home/arista/.local/bin

# Verify path
$ echo $PATH

# Create a virtual env named .venv
$ virtualenv -p $(which python3) .venv

# Activate virtualenv
$ source .venv/bin/activate
```

## Install Python requirements

```shell
$ pip install --requirement requirements.txt

# Check what has been installed
$ pip list

# Install sshpass. This is problematic on MACs. Need to download Xcode. Run it. Go to Preferences>Downloads>Command Line tools 
# on the Install button. Follow the sshpass installation here 
# https://www.hashbangcode.com/article/installing-sshpass-osx-mavericks#:~:text=You%20can%20do%20this%20by,project%2C%20currently%20available%20on%20sourceforge.
$ sudo apt-get install -y sshpass
```

## Install the Arista CVP and AVD collections

```shell
# Create a folder for the Ansible collections
$ cd labs
$ mkdir collections
$ cd collections

# Install the Arista CVP collection
$ git clone https://github.com/aristanetworks/ansible-cvp.git

# Install the Arista AVD collection
$ git clone https://github.com/aristanetworks/ansible-avd.git

```

## Configure CloudVision IP Address

> Inventory is pre-configured with internal CVP IP address, so it is not required to update this file.

Go to [`labs`](../labs/) folder:

```shell

$ cd ..

# Display inventory file
$ cat inventory.yml

```
