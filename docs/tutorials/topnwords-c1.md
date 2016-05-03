Setting up your development environment
=======================================

To begin with, please follow the steps outlined in:
[Apache Apex Development Environment Setup](../apex_development_setup.md)
to setup your development environment; you can skip the sandbox download
and installation if you already have a Hadoop cluster with Datatorrent
RTS installed where you can deploy applications.

Sample input files
------------------
For this tutorial, you need some sample text files to use as input to the application.
Binary files such as PDF or DOCX files are not suitable since they contain a
lot of meaningless strings that look like words (for example,  &ldquo;Wqgi&rdquo;).
Similarly, files using markup languages such as XML or HTML files are also not
suitable since the tag names such as  `div`, `td` and `p` dominate the word
counts. The RFC (Request for Comment) files that are used as de-facto
specifications for internet standards are good candidates since they contain
pure text; download a few of them as follows:

Open a terminal and run the following commands to create a directory named
`data` under your home directory and download 3 files there:

    cd; mkdir data; cd data  
    wget http://tools.ietf.org/rfc/rfc1945.txt  
    wget https://www.ietf.org/rfc/rfc2616.txt  
    wget https://tools.ietf.org/rfc/rfc4844.txt
