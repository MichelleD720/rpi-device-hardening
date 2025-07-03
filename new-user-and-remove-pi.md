**Article ID:** KB-RPI-0006
**Last Updated:** 2025-07-02  
**Author:** Michelle Dang   
**Category:** Raspberry Pi → Security 
**Related Articles**

## new-user-and-remove-pi 

### Creating the new User 
6.1 First ssh into the pi and add the new user sudo adduser (chosen name)
![{6871EA96-283F-4A4E-B690-93E2B5F1707F}](https://github.com/user-attachments/assets/53038a13-81d4-4563-ac2f-cd29eedd01a1)

6.2 Add the Password. It's normal for the characters not to show. This is a linux security feature 
![{4B3B9545-01AF-4EF1-A2B5-AE119F97E9C6}](https://github.com/user-attachments/assets/61ef0885-5aef-4f3c-aada-6b3f9fa6a40a)

6.3 Keep hitting enter until it ask you to put in y/n. Put in N
![{B1E9CF92-F4F1-4E1F-8784-B20A8BA03763}](https://github.com/user-attachments/assets/3d456cfa-5114-4964-a50d-27ddf4b53067)

6.4 Next type in sudo usermod -aG sudo username this command. This command adds an existing user to the sudo group, which gives them permission to run commands with sudo (i.e., superuser privileges). 
Now hit enter. Nothing will change 

6.5 Now we need to type in sudo nano /etc/lightdm/lightdm.conf This will open LightDM which is a display manager that handles the graphical login screen on many Linux distributions. 
![{0BC56176-95EE-4701-90C7-D63692506B56}](https://github.com/user-attachments/assets/4015cea9-196e-4b4b-8515-0d12e1b9fc88)
![{FD9D695E-AA94-49A8-817D-18105211ECEE}](https://github.com/user-attachments/assets/295d182b-8652-4e6f-8d4d-a310d2a8ba82)

6.6 Do crtl + w to pull up the search function and type in autologin-user=
![{9515CDA1-9C07-4B49-96CE-B6F7B01D891D}](https://github.com/user-attachments/assets/f8baf519-bc22-4f2b-9a70-16b4ffad2a18)

6.7 Change pi to your user name. Then do Crtl+O for write out to save changes. Then hit enter. Followed by Crtl+ X 
![{665E30D0-AC90-40BB-86F9-5E91112E44B8}](https://github.com/user-attachments/assets/ad6959fd-a077-4faf-b846-5418b4ae32d1)

6.8 finally do sudo reboot and try to ssh into your new user 


## How to remove the default pi 
6.9 first ssh into the new user account you just created. Then type in sudo userdel -r pi . This will delete the pi user. If it does not then go to 6.10
### WARNING if you attempt to delete pi while ssh into the pi user you will break the system.Same principle for any account deletion. Do not delete the user you are currently logged into.

6.10 ssh into your new user account. Then sudo raspi-config->1-> S6 and turn off autologin,reboot, and try to redo 6.9
![{831B401A-FA59-44CD-BAFC-8563C5B10919}](https://github.com/user-attachments/assets/cd1b779f-a0ee-4cda-bc16-f153b97b3582)














