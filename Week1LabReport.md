# Week 1 Lab Report

## Step 1 - Installing VSCode:

- Go to this website: [Link](https://code.visualstudio.com/)
- You should see this:
<img width="1508" alt="image" src="https://user-images.githubusercontent.com/63521936/211926793-2043020a-32f2-405f-bf92-0b8104e7a297.png">
- Click on the download button (circled in the image) and follow the steps shown to you to properly install VSCode


- Once downloaded, you should see something like this:
<img width="1026" alt="image" src="https://user-images.githubusercontent.com/63521936/211928276-71934894-e91d-4ee0-bcc5-129303dd750a.png">

## Step 2 - Remote Connection:
- Open up the Terminal in VSCode, which can be found at the bottom
- In the Terminal, type in ssh (name of your course-specific account), like this:
<img width="809" alt="image" src="https://user-images.githubusercontent.com/63521936/211928724-f2fd810a-270b-466a-b63b-6d37defb5b19.png">
- You will then probably get a message like this:
<img width="610" alt="image" src="https://user-images.githubusercontent.com/63521936/211928851-a38fbc2a-a58c-4ac9-812b-ab43eb93dc3f.png">
- Type yes, and when prompted for your password enter the password for your account
- Once you enter your password, you should see an output like this:
<img width="787" alt="image" src="https://user-images.githubusercontent.com/63521936/211929155-f19dfffd-9095-41f1-a0bb-3bd265e45747.png">
**You are now remotely connected!**

## Step 3 - Trying Some Commands

- Now that you are remotely connected, you can try using some commands in your terminal

These commands include:

> cd ~
> cd
> ls -lat
> ls -a
> ls <directory> where directory is /home/linux/ieng6/cs15lwi23/(*someone's account name*)
> cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/
> cat /home/linux/ieng6/cs15lwi23/public/hello.txt
