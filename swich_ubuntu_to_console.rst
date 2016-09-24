===========================
Switch GUI Ubuntu to Console.
===========================
sudo sh -c 'echo manual >> /etc/init/lightdm.override'
sudo sh -c 'echo manual >> /etc/init/bluetooth.override'
sudo sh -c 'echo manual >> /etc/init/cups.override'
sudo sh -c 'echo manual >> /etc/init/cups-browsed.override'
sudo reboot
