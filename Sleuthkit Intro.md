🚩 picoCTF - Sleuthkit Intro (Forensics)

📊 Challenge Information

Category: Forensics

Difficulty: Easy

Tools used: mmls (The Sleuth Kit), netcat (nc)

🕵️‍♂️ Investigation Process

Analyze the target: We are given a compressed disk image disk.img.gz.

Decompress the file: First, decompress the image using gunzip:

gunzip disk.img.gz


Inspect the Partition Table: To find the size of the partition, we use the Sleuth Kit tool mmls to display the layout of the disk image:

mmls disk.img


Output structure:

DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   002047999    00202752     Linux (0x83)


Identify the Partition Length: Looking at the Linux partition (Slot 002), the starting sector is 2048 and the length is 202752 sectors.

Retrieve the Flag: Connect to the challenge remote server using nc (netcat) and provide the partition size in sectors (202752) when prompted:

nc saturn.picoctf.net <PORT_NUMBER>


After entering the correct length, the server outputs the flag.

🎯 Flag

picoCTF{mm15_f7w_p4rt1t10n_sh0w_e02c1187} (Note: Replace with your actual dynamic flag received from netcat)
