---
layout: post
title:  "Text Conversion"
subtitle: "[Insert witty comment here.]"
date:   2017-07-17 16:28:45
categories: [tool]
---

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
pandoc replication-and-decline.md --latex-engine=pdflatex -o replication-and-decline.pdf

echo "Converting paper to LATEX document."
pandoc -S -o $file.tex $file.md

echo "Converting paper to TXT document."
pandoc -S -o $file.txt $file.md

# Make the command line read "Converted INPUT-FILENAME to HTML, DOCX, ODT, PDF, TXT, and TEX"
echo "Coverted $file to HTML, DOCX, ODT, PDF, TEX, and TXT."
{% endhighlight %}

Link Address: http://jekyll-tylercartergse2013485235.codeanyapp.com:4000/replication-and-decline.docx
