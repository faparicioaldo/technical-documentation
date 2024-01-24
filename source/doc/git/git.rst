
===========
global and local config
===========
git config --list
git config --global --list

Add local config that override the global one
to use another email for the other repo

git config user.name "Aladdin"\n
git config user.email "faparicioaldo@gmail.com"\n

============
add other key for other mail
============
Create a new key pair with another email 

ssh-keygen -t rsa -b 4096 -C "tu_email@example.com" -f ~/.ssh/id_rsa_personal

by default 2048 but 4096 is safer

Add the new private key to the agent  
ssh-add ~/.ssh/id_rsa_personal

Confirm if the key was added to the agent 
ssh-add -l (or -L for more details) 

Delete if wrong 
ssh-add -d ~/.ssh/id_rsa_personal

===========
Config for multiple ssh users same machine  
===========

Create a 
~/.ssh/config

with the permissions
chmod 600 ~/.ssh/config

"""
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa

Host github-personal.com
  HostName github.com
  User git-personal
  IdentityFile ~/.ssh/id_rsa_personal
"""

Then when can interact with other git repos using the host alias 
the condig file will handle the conversion to the real host

git clone git@github-att:user/att-repo.git

I saw the user do not matter, we can use any user when clone, but be aware of that

If neccesary we can kill the agent, only if neccesay 
ssh-agent -k  # Kill the current agent
eval "$(ssh-agent -s)"  # Start a new agent
ssh-add ~/.ssh/id_rsa_personal  # Add your private key to the agent

