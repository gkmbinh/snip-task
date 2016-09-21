first compaire with this.
File SSHD_CONFIG on amazon service 
:: 
  # Package generated configuration file
  # See the sshd_config(5) manpage for details
  
  # What ports, IPs and protocols we listen for
  Port 22
  # Use these options to restrict which interfaces/protocols sshd will bind to
  #ListenAddress ::
  #ListenAddress 0.0.0.0
  Protocol 2
  # HostKeys for protocol version 2
  HostKey /etc/ssh/ssh_host_rsa_key
  HostKey /etc/ssh/ssh_host_dsa_key
  HostKey /etc/ssh/ssh_host_ecdsa_key
  HostKey /etc/ssh/ssh_host_ed25519_key
  #Privilege Separation is turned on for security
  UsePrivilegeSeparation yes
  
  # Lifetime and size of ephemeral version 1 server key
  KeyRegenerationInterval 3600
  ServerKeyBits 1024
  
  # Logging
  SyslogFacility AUTH
  LogLevel INFO
  
  # Authentication:
  LoginGraceTime 120
  PermitRootLogin without-password
  StrictModes yes
  
  RSAAuthentication yes
  PubkeyAuthentication yes
  #AuthorizedKeysFile	%h/.ssh/authorized_keys
  
  # Don't read the user's ~/.rhosts and ~/.shosts files
  IgnoreRhosts yes
  # For this to work you will also need host keys in /etc/ssh_known_hosts
  RhostsRSAAuthentication no
  # similar for protocol version 2
  HostbasedAuthentication no
  # Uncomment if you don't trust ~/.ssh/known_hosts for RhostsRSAAuthentication
  #IgnoreUserKnownHosts yes
  
  # To enable empty passwords, change to yes (NOT RECOMMENDED)
  PermitEmptyPasswords no
  
  # Change to yes to enable challenge-response passwords (beware issues with
  # some PAM modules and threads)
  ChallengeResponseAuthentication no
  
  # Change to no to disable tunnelled clear text passwords
  PasswordAuthentication no
  
  # Kerberos options
  #KerberosAuthentication no
  #KerberosGetAFSToken no
  #KerberosOrLocalPasswd yes
  #KerberosTicketCleanup yes
  
  # GSSAPI options
  #GSSAPIAuthentication no
  #GSSAPICleanupCredentials yes
  
  X11Forwarding yes
  X11DisplayOffset 10
  PrintMotd no
  PrintLastLog yes
  TCPKeepAlive yes
  #UseLogin no
  
  #MaxStartups 10:30:60
  #Banner /etc/issue.net
  
  # Allow client to pass locale environment variables
  AcceptEnv LANG LC_*
  
  Subsystem sftp /usr/lib/openssh/sftp-server
  
  # Set this to 'yes' to enable PAM authentication, account processing,
  # and session processing. If this is enabled, PAM authentication will
  # be allowed through the ChallengeResponseAuthentication and
  # PasswordAuthentication.  Depending on your PAM configuration,
  # PAM authentication via ChallengeResponseAuthentication may bypass
  # the setting of "PermitRootLogin without-password".
  # If you just want the PAM account and session checks to run without
  # PAM authentication, then enable this but set PasswordAuthentication
  # and ChallengeResponseAuthentication to 'no'.
  UsePAM yes

Left compaire with your file /etc/ssh/sshd_config 

for deeplearning robot :
left uncommand PasswordAuthentication yes, become like as.
::
  # Change to no to disable tunnelled clear text passwords
  PasswordAuthentication yes
  
#====================================== CREATE PEM FILE TO SSH WITHOUT PASSWORD

create pub key, priv key.
https://help.ubuntu.com/community/SSH/OpenSSH/Keys
Generating RSA Keys

The first step involves creating a set of RSA keys for use in authentication.

This should be done on the client.

To create your public and private SSH keys on the command-line:
::
  mkdir ~/.ssh
  chmod 700 ~/.ssh
  ssh-keygen -t rsa

You will be prompted for a location to save the keys, and a passphrase for the keys. This passphrase will protect your private key while it's stored on the hard drive:
::
  
  Generating public/private rsa key pair.
  Enter file in which to save the key (/home/b/.ssh/id_rsa):
  Enter passphrase (empty for no passphrase):
  Enter same passphrase again:
  Your identification has been saved in /home/b/.ssh/id_rsa.
  Your public key has been saved in /home/b/.ssh/id_rsa.pub.

Your public key is now available as .ssh/id_rsa.pub in your home folder.

Congratulations! You now have a set of keys. Now it's time to make your systems allow you to login with them 


then create pem file.
::
  openssl rsa -in ~/.ssh/id_rsa -outform pem > id_rsa.pem



