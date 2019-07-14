# Automatic IPA server setup powered by Ansible and Vagrant. 

## Required software before setting up:
- Ansible - (`yum install ansible` or `brew install ansible`)
- Python - (`yum install python`or `brew install python`)
- [Vagrant](https://www.vagrantup.com/downloads.html) - (`brew cask install vagrant`)
- [Virtualbox](https://www.virtualbox.org/wiki/Downloads) (`brew cask install VirtualBox`)
- SSHPASS `brew install https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb`
### Install at once with the command below:
`brew install ansible ; brew install python ; brew cask install vagrant ; brew cask install VirtualBox ; brew install https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb`

## Set Up Instructions
1. Create a seperate `/bin` directory and `cd` to it. 
2. Clone the environment repo to it with `git clone https://github.com/rdbreak/ipasetup.git`
3. Run `vagrant up --provider virtualbox` to deploy the environment _(You must be in the directory you cloned the repo to in order to run vagrant commands.)_

*Also, don't be spooked by any red font during the setup process. It won't have an affect on your exam environment* 

_NOTE - You can use the VirtualBox console to interact with the VMs or through a terminal. If you need to reset the root password, you would need to use the console though._

The first time you run the vagrant up command, it will download the OS images for later use. In other words, it will take longest the first time around but will be faster when it is deployed again. You can run `vagrant destroy -f` to destroy your environment at anytime. **This will erase everything**. This environment is meant to be reuseable, If you run the `vagrant up --provider virtualbox` command after destroying the environment, the OS image will already be downloaded and environment will deploy faster. Once the setup is complete, the ipa server EXAMPLE.COM will already be setup and paired. Deployment should take around 15 minutes depending on your computer. You shouldn't need to access the IPA server during your practice exams. This setup assumes you have another server that you would pair it with under the REALM `EXAMPLE.COM`. You can change all of these settings by adjusting the VagrantFile and or ipa.yml file. Hope this helps you in your studies!

### It includes three systems:
- ipa.example.com

### Network Details:
###### system1
192.168.55.30

### Local users
- Username = vagrant
- Password = vagrant (if prompted)
- For root = use `sudo` or `sudo su`

How to access from terminal - `ssh vagrant@192.168.55.30`

## Help
If you're having problems with the environment, please submit an issue by going to the `ISSUE` tab at the top. If you have more questions, looking for practice exams to use against this environment, or just looking for a fantastic Red Hat community to join, please navigate to #practiceexam in the [Red Hat Certs Slack Workspace](https://join.slack.com/t/redhat-certs/shared_invite/enQtNjAxNDc3MzYyMTAxLWZlM2ZhMGRlNGI2YjQyMzQ4NWEyNDIyYTJiNzcxM2E1ZDVkZmQ4MzU2MTc0ZDRlNzg2MTU5NWIwZjFjZDdjMGE).