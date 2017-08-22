---
layout: post
title:  "Text Conversion"
subtitle: "[Insert witty comment here.]"
date:   2017-07-17 16:28:45
categories: [tool]
---

This page is dedicated to my one and only true friend, sanjorge11.

Below is a script written to convert a document in markdown to a variety of document types, such as HTML, ODT, DOCX, etc. When the script is run, the user will be notified along the way which document type is being produced from the conversion script.

To get it into multiple formats, we utilizted pandoc's document conversion toolset. The script executes the pandoc -S -o [*.(desired document conversion type)] [(original.md)]

Here is the code used in the script.

{% highlight ruby %}
#!/bin/bash

# Declare input argument as a variable
file=replication-and-decline

# Convert markdown to HTML
echo "Converting paper to HTML document."
pandoc -S -o $file.html $file.md

# Convert markdown to DOCX
echo "Converting paper to DOCX document."
pandoc -S -o $file.docx $file.md

# Convert markdown to ODT
echo "Converting paper to ODT document."
pandoc -S -o $file.odt $file.md

# Convert markdown to PDF
echo "Converting paper to PDF document."
pandoc -o $file.pdf --latex-engine=pdflatex $file.md

# Convert markdown to TEX
echo "Converting paper to LATEX document."
pandoc -S -o $file.tex $file.md

# Convert markdown to TXT
echo "Converting paper to TXT document."
pandoc -S -o $file.txt $file.md

# Make the command line read "Converted INPUT-FILENAME to HTML, DOCX, ODT, PDF, TXT, and TEX"
echo "Coverted $file to HTML, DOCX, ODT, PDF, TEX, and TXT."
{% endhighlight %}

Document available in forms below:
- [MD][1]
- [HTML][2]
- [DOCX][3]
- [ODT][4]
- [PDF][5]
- [TEX][6]
- [TXT][7]


[1]:tylerpcarter.github.io/download/replication-and-decline.md
[2]:tylerpcarter.github.io/download/replication-and-decline.html
[3]:tylerpcarter.github.io/download/replication-and-decline.docx
[4]:tylerpcarter.github.io/download/replication-and-decline.odt
[5]:tylerpcarter.github.io/download/replication-and-decline.pdf
[6]:tylerpcarter.github.io/download/replication-and-decline.tex
[7]:tylerpcarter.github.io/download/replication-and-decline.txt
