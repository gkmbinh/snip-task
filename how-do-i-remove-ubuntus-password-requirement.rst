=====================
How do I remove Ubuntu's password requirement sudo
=====================
For the administrative password using sudo and sparing any lectures on why one would not want this...

Edit the sudoers file:

sudo visudo
Find this line:
::
  %sudo ALL=(ALL) ALL

Change the line:
::
  %sudo ALL=(ALL) NOPASSWD: ALL

Save and Exit. Voila! (Dont' shoot yourself in the foot, now. ;)

By the way, you can become root and just type the password once.
::
  sudo su -

Now you ARE the root user, seeing no more password prompts. When you see guides referring to commands such as sudo some_command, just remove the "sudo" portion. In this way, you can choose to leave the security intact yet bypass it as you see fit

If you are writing about your user account:

Open System Settings. Click on the User Accounts tile. Click the Unlock button and enter your password. Set the auto-login slider to the "on" position by dragging it to the right. Then click "Lock" to apply your changes.
