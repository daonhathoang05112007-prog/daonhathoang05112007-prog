🚩 picoCTF - Enhance! (Forensics)

📊 Challenge Information

Category: Forensics

Difficulty: Easy

Tools used: Text Editor / cat

🕵️‍♂️ Investigation Process

Identify the file type: The challenge provides a file named drawing.flag.svg. SVG is a vector image format that is entirely XML/text-based.

Inspect source code: Since it's a text-based file, I decided to read its source code directly using cat in the terminal:

cat drawing.flag.svg


Analyze structure: Inside the SVG tags, I noticed that the flag was not in a single line. Instead, it was split character-by-character inside multiple <tspan> tags to bypass simple search scripts (grep).

Assembly: I manually (or using basic string cleaning) assembled the scattered parts from each <tspan> block to reconstruct the full flag.

🎯 Flag

picoCTF{3nh4nc3d_d067425b}
