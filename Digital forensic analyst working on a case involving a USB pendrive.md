## Imagine you're a digital forensic analyst working on a case involving a USB pendrive suspected to contain crucial evidence. Detail the steps you would take to acquire the evidence and recover files from the pendrive using the following tools: Guymager for creating a dd file, and Foremost for file recovery. Explain each step of the process, from connecting the pendrive to your forensic workstation to generating a dd file using Guymager, and then recovering files using foremost.

FIRST We would insert our usb drive.

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/79f2ca85-e615-4e69-9571-957536a3d784)

Then i am going to delete the `tree.jpeg` image from this usb.

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/92dabdc0-2a2b-4f4b-b948-e69b6eb9decd)

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/167d6e5b-7ed2-4ec5-a260-cb1d46166c64)

now we will use guymager

### Guymager 

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/e17f3c8f-4f70-46d8-a1cb-b0b6e0f296d1)

Here we can see that we can clone the pen drive on our hard disks or any other flash drives. To acquire image we need to right click on the disk and select the acquire option.

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/d11635a8-dfa1-4bf9-875f-5fca6f063f4e)

Here we can choose the file format and provide the case number and evidence number, examiner, descriptions and notes. Here we can also choose the image directory. We can also split the size of disk. We can calculate MD% and SHA1 and SHA-256. Then we must check the verification process, because if the image acquisition was not valid then it can't be an evidence. So verification is a good habit. Here we have done everything, and set the acquired image directory in our desktop, and we did not used the split image because we are not acquiring large image. Following screenshot shows the process.

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/8f7d5912-6ccc-426b-ba80-31e8c7f42ac9)

After finishing we will get image

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/623e7b32-9829-4c5d-a4ce-e54d5a619f74)

now we will use dd image to recover the image by using Foremost tool

## Foremost

man foremost

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/be96a81a-92f4-4a3b-ab39-69f2b24c97ea)

The syntax for using Foremost is as follows:

`foremost -i (forensic image) -o (output folder) -options`

To recover the jpg image from from the dd image file, use the following command syntax:

`foremost -t jpg -i <input_file> -o <output_directory>`

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/328fb5f1-62fa-48c0-89e8-34d1224245e6)

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/9302b528-3496-4f53-9ef1-5803987ff1bd)

![image](https://github.com/RahulMMenon011/Cyber_Forensics/assets/140642506/d7e7ffc3-4981-4818-b110-5930ec0b8ae7)

It has succesfully recovered the tree.jpeg image


