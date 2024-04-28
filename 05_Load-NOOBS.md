# Load NOOBS:

- Navigate to https://www.raspberrypi.org/downloads/noobs/

- This is where you will download the NOOBS zip file.

- I specifically chose to use NOOBS instead of NOOBS Lite because I wanted to have the desktop and the rest of the bells and whistles. The Noobs Lite seems to be better suited if you are building a headless node, which I did not.

- As of this writing, NOOBS version 3.2.1 = 
SHA256:9d040a0b2795e940cab848c612a9ccfd739cf7ea5fcb1d42141f93cefcef4078

- You can use Windows to check SHA256.

- Launch Windows Power Shell (not the CMD.exe)

- From C:/ type "Get-FileHash" Followed by your file path, ending with filename.

- For example: "PS C:\> Get-FileHash C:\Users\your_user\Desktop\Raspberry_Pi\NOOBS_v3_2_1.zip"

- Note, Windows Power Shell does not like spaces in your file-path, use an underscore where needed instead.

- If your SHA256 result does not match, you should not proceed, you may have a compromised file.

- Extract the contents of the zip file.

- Copy all contents of the extraction to the newly formatted 64GB MicroSD card.

- Safely eject the MicroSD card and while the Raspberry Pi is still shut off, and after the board has been installed in the case, install the MicroSD card in the MicroSD card port.
