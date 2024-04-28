# Format The MicroSD Card:

- Your Raspberry Pi may have come with a preloaded 64GB MicroSD, in which case you can skip this section. But the point of this section is to get the NOOBS image loaded on your MicroSD Card.

- Format a 64GB MicroSD card on a seperate computer.

- This will be your boot disc for the Raspberry Pi.

- Make sure it is formated to the FAT32 file system.

- You might be prompted that the microSD card needs to be formatted before your computer can talk to it. It may be necessary to format it to exFAT with your native disc manager first if FAT32 is not an initial option.

- Windows disc manager, for example, is accesible by opening your file explorer, right clicking on "This PC", and selecting "Manage".

- There, you can right-click the appropriate drive and select 'format' and then follow the prompts.

- The Raspberry Pi boot drive you are creating needs to be formatted to FAT32.

- In my situation, Windows10 did not give me the option of formatting to FAT32, only exFAT.

- My solution was to download GuiFormat.exe from
http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm

- GuiFormat.exe will allow you to format the MicroSD card to FAT32 through the easy to follow prompts.
