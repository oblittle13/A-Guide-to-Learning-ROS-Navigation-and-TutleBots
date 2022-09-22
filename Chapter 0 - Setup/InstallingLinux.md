In my specific case, I'm using a Dell XPS 15 7590 from 2019. There were a few hick ups along the way, but that's what google search is for. We are going to need Ubuntu install 20.04 for this.

What I Tried First:
 
 1. Firstly, I tried to install Linux by using a VM, specifically [VirtualBox VM by Oracle](https://www.virtualbox.org).
 2. This actually worked great for my WS MoveIt Panda Arm. However, there is an issue when it comes to this: I need to SSH into a seperate laptop that controls the TurtleBot. Why is this an issue? When using a VM inside of windows, I don't get real access to the ports (network port in this case) on my laptop, since Windows is "in control" of them. So I wasn't able to SSH into the other latop. Back to the drawing board.

The Solution that Worked, but Needed a Little Assistance:

1. Normally, installing Linux along side Windows is relatively easy. Just follow one of thousands of tutorials o the internet and you're set. However, the Dell XPS 15 7590 has some BIOS settings that prevent it. In order to fix it I follows [This tutorial from Tyler Lum](https://medium.com/@tylergwlum/my-journey-installing-ubuntu-18-04-on-the-dell-xps-15-7590-2019-756f738a6447).
2. Next, we need to install an image of of Ubuntu 20.04 onto a USB stick.
   - You'll need at least 25 GB of free space on your Windows machine. This is the same that Ubuntu will occupy.
   - You'll also need a USB drive with 8 GB of space to hold the Ubuntu image on it.
   - In order to download the image [Download it from this page](https://ubuntu.com/download/desktop).
   - While your image downloads, we need to make the USB a bootable device in Windows. In order to do this we need to:
     - Install a program called [Rufus](https://rufus.ie/en/).
     - Once Rufus has installed, open it. In the GUI make sure you select your USB that you want to install the Ubuntu Image on. (Note: All the contents of the USB drive will be erased.)
     - In the `boot selection` drop down, select your ISO image you downloaded earlier.
3. While Rufus is doing its thing, there's a very important step we have to do, disable BitLocker. 
   - The best way to do this is from the command line. Launch the command line in administrator mode.
   - Then type the following: `manage-bde -odd C:` (Note: Repalce "C:" with the name of your drive that holds windows.).
   - If it says that it needs your encryption key, [Click here](https://support.microsoft.com/en-us/windows/finding-your-bitlocker-recovery-key-in-windows-6b71ad27-0b89-ea08-f143-056f5ab347d6) for steps on how to find it. You may need to input it after "C:" in the command above, I did not in my case.
   - Your device should now start decrypting your drive. This will take a bit, but should take around the same amount of time as Rufus. Go get a coffee and a donut, I prefer Honey Cruelers as my go to.
   - At any time, you can check on your BitLocker status by typing `manage-bde -status` in the command line. Look for `Conversion Status`, if that says `Fully Decrypted` then you're good to go!
4. Once your decryption has finished and Rufus has finished doing its thing, we are ready to restart your computer. Make sure the USB device stays pluged when you restart. You'll need to mash your boot manager BIOS startup key in order to open into the Boot Manager menu. For my specific case its the `F12` key, yours may be another function key or `ESC` or `Delete`. Look for this online before you restart, otherwise you may end up restarting multiple times trying to find the right key.
   - Make sure you follow all the prompts when you launch into the Ubuntu Installer. We want to install along side windows, if you choose another option, you may risk wiping your drive. Make sure to select `Install Ubuntu` rather than `Try Ubuntu`.
