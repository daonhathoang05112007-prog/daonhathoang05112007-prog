🚩 picoCTF - Glory of the Garden (Forensics)

📊 Challenge Information

Category: Forensics

Difficulty: Easy

Tools used: strings, grep (Linux CLI) or Hex Editor

🕵️‍♂️ Investigation Process

-Analyze the file: We are given an image named garden.jpg.

-Search for plaintext: Usually, simple forensics challenges hide the flag as raw ASCII text at the very end of the file.

-Method 1 (Command Line - Quickest): I used the strings command to extract printable characters from the binary and filtered the output for "pico":

strings garden.jpg | grep "pico"


M-ethod 2 (Hex Editor): Alternatively, opening the image in a Hex Editor (like HxD or Hexed.it) and scrolling down past the standard JPEG end-of-file marker (FF D9) reveals the flag written in plain text.

🎯 Flag

picoCTF{m0r3_th4n_m33ts_th3_3y3e5b3g379}
