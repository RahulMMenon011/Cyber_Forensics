# Cyber Forensic Experiment

### Rahul M Menon
### CB.SC.P2CYS23015

Investigating a suspicious USB pendrive found at a crime scene. The forensic team needs to acquire evidence from the pendrive while ensuring the integrity of the data. Using the dd and dc3dd commands, create a forensic image (.img) file of the pendrive. Additionally, generate a SHA-256 hashfile for the image file to verify its integrity. Finally, wipe the pendrive using the disk wipe pattern 00011 to prevent any potential data leakage. Run the commands and take a snapshot and submit it in a word document

Inserting the usb drive and running the fdisk -l command

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/655d00c7-378d-43fc-8a6a-766c6c6ea4fe)

Creating the disk image of inserted USB drive

`dd if=/dev/sdb1 of=disk.img`

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/79779764-fc82-4392-a767-210edc331ff5)

Now we verify the created disk image file and then delete it

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/b6cb16d4-7714-4141-b8f5-a3e20345804a)

We can also create disk image by explicitly specifying block size and adding error handling to it

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/b4d268be-2c13-47ac-9198-75641d173128)

### DC3DD

Now we install DC3DD

man DC3DD

`dc3dd if=/dev/sdb hash=sha256 log=split_usb ofs=test.img.000 ofsz=500M`

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/266a1908-5900-441a-8edc-5082d2aeb28e)

We will insert usb disk again and make a disk image using DC3DD

We have to split usb with the help of dc3dd tool

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/25d085a6-0128-4e2f-b176-5b8e386801b6)

The hash=sha256 parameter generates the SHA 256 of the created disk image. It is present in the results

verifying the segments using ls command

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/e9eadcf6-67e8-4b5f-84db-8ff1608ec2ac)

Then we can permanently wipe the data from the usb drive using this command with text pattern 

`dc3dd wipe=/dev/sdb tpat=cfsi`

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/56a835db-1fc6-4656-ac07-a6301ba6075a)

now we type fdisk –l again

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/87c76e57-40f8-4577-9321-87da6b3d0b27)

we can also use Binary pattern to wipe the data in usb drive instead of text pattern

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/86ebec09-1070-4e65-af16-ca8b77ad9a00)



