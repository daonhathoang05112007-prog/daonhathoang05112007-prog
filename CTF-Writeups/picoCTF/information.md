🚩 picoCTF - information (Forensics)

📊 Challenge Information

Category: Forensics

Difficulty: Easy

Tools used: exiftool, base64 (Linux CLI)

🕵️‍♂️ Investigation Process

1.Analyze the target: I downloaded the challenge file named cat.jpg. Since the challenge is titled "information", it strongly hints at metadata hidden inside the file.

2.Examine Metadata: I ran exiftool to inspect all metadata embedded in the image:

-exiftool cat.jpg

3.Find the anomaly: Looking at the output, the License field contained a long, suspicious Base64 encoded string:
-Base64 String: cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfcmVhbGx5X2Nvb2xfZDBiY29mM3N9

4.Decode: I decoded this Base64 string using the Linux terminal:
-echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfcmVhbGx5X2Nvb2xfZDBiY29mM3N9" | base64 -d

🎯 Flag

-picoCTF{the_m3tadata_1s_really_cool_d0bcof3s}
