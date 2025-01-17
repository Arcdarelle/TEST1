Introductory note
=================

Important notes before starting this course.
--------------------------------------------

1.  **Server prerequisite** : Throughout this course, we use a server to answer questions 1 to 20. **Note:** You will find 21 questions here because the root password  reset (Q14) was taken as a question. Before starting, download the server by [clicking here](https://utrains.s3.amazonaws.com/classmaterials/REDHAT8EXAM.ova).
    
2.  Go through the following slide to import the server in your Virtualbox and to break the root password in order to access the server.  **Note:** If you face any issue importing the server, follow the slide after this[**Click here to download the slide**](https://docs.google.com/presentation/d/1AOYQGSnG57a0PfAvuLoREwakspHRKilHwnBvtKGZVxo/edit?usp=sharing)

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRad-IVF1m6x-9OnCaFTklEmYA_uNNU0qTViLBUxwrCjACgytU44FlX6qQt3WPOu2NLfqfE8aAVPhuv/embed?start=false&amp;loop=false&amp;delayms=3000" width="960" height="569" frameborder="0" allowfullscreen="allowfullscreen"></iframe>
    
4.  If you encounter an issue while starting the imported server, follow this slide to solve the issue[**Click here to download the slide**](https://docs.google.com/presentation/d/15ol5UGQx4xS1S-RZuRl-miXQFalCJoHh___sNV1uGx8/edit?usp=sharing)
    
5.  **Reference to old platform** : Throughout this course, the instructor may use an older platform to download tools used in the course. We no longer use that platform. Please disregard those parts of the videos that use the old platform.
    
6.  If you are taking the exam from home, [this document](https://drive.google.com/file/d/1Zx4hnpsBzMM3_rG54ZW3lW2pXgnXCmRR/view?usp=sharing) will guide you throughout your preparation.
    

In the exam hall...
-------------------

1.  Read the instruction very very carefully!!!!
    
2.  You will have two VMs with CLI as **node1.example.com** and **node2.example.com** (Minimal Server)
    
3.  You will need to break the “root” password on the **node2.example.com** and then reset it to “**ringogee**” 
    
4.  You will need to set the “hostname” according to Exam instruction.
    
5.  You will need to set static IP address/Netmask/Gateway/DNS according to Exam instructions.
    

Before the exam, you might be asked to fill an online form with questions about how you studied for this. Also, you will need to fill in your name, your address, your email, accept Rules Agreement and then submit.

**Note: you will get 3 disks on the virtual machine**

1.  /dev/vda ==> OS Installed
    
2.   /dev/vdb ==> To create partition( lvm and swap) (Pre-created partitions available)
    
3.  /dev/vdc ==> for Stratis pool, filesystem and snapshots or VDO volume
