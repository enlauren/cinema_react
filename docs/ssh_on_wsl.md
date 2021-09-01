If you're running Ubuntu on Windows Subsystem for Linux, there will not be a preinstalled public key or authorized keys list, so you'll need to generate your own.

If you don't already have openssh-server installed:

1. `sudo apt-get upgrade`
2. `sudo apt-get update`
3. `sudo apt-get install openssh-server`
4. `sudo service ssh start`

Then take the following steps to enable sshing to localhost:`

1. `cd ~/.ssh`
2. `ssh-keygen` to generate a public/private rsa key pair; use the default options
3. `cat id_rsa.pub >> authorized_keys` to append the key to the authorized_keys file
4. `chmod 640 authorized_keys` to set restricted permissions
5. `sudo service ssh restart` to pickup recent changes
6. `ssh localhost`

link: https://stackoverflow.com/questions/28210637/unable-to-ssh-localhost-permission-denied-publickey-connection-closed-by