This is a simple tutorial to convert XML to CSV format using XMLUTILS.py
We can use this python utility to convert XML to CSV, JSON and SQL.
Blind conversion of XML to CSV and SQL is not recommended. It only works if the structure of the XML document is simple (flat). 

Click on window icon and go to your command window.

---Install with xmlutils.py using the following command.

pip install xmlutils

---xml2csv Convert an XML document to a CSV file.

xml2csv --input "samples/fruits.xml" --output "samples/fruits.csv" --tag "item"


---Arguments
--input 	Input XML document's filename*
--output 	Output CSV file's filename*
--tag 		The tag of the node that represents a single record (Eg: item, record)*
--delimiter 	Delimiter for separating items in a row. Default is, (a comma followed by a space)
--ignore 	A space-separated list of element tags in the XML document to ignore
--noheader 	Exclude CSV fields header (first line). Off by default
--encoding 	Character encoding of the document. Default is utf-8
--limit 	Limit the number of records to be processed from the document to a particular number. The default is no limit (-1)
--buffer 	The number of records to be kept in memory before it is written to the output CSV file. Helps reduce the number of disk writes. Default is 1000

Make sure you are using python version 2.7 version. This library is verified on it.


***Error for using other versions of Python.
from xmlutils.xml2csv import xmlcsv
Traceback (most recent call last):
File "", line 1, in 
ImportError: cannot import name 'xmlcsv'
from xmlutils.xml2csv import xml2csv
converter = xml2csv("samples/fruits.xml", "samples/fruits.csv" , encoding =
"utf-8")
coverter.convert(tag = "item")
Traceback (most recent call last):
File "", line 1, in 
NameError: name 'coverter' is not defined
converter.convert(tag = "item")
Traceback (most recent call last):
File "", line 1, in 
File "c\Python Folder\xmlutils.py\xmlutils\xml2csv.py",
line 56, in convert
event, root = self.context.next()
AttributeError: '_IterParseIterator' object has no attribute 'next'
converter.convert(tag = "item")
Traceback (most recent call last):
File "", line 1, in 
File "c\Python Folder\xmlutils.py\xmlutils\xml2csv.py",
line 56, in convert
# event, root = self.context.next()
AttributeError: '_IterParseIterator' object has no attribute 'next'
converter.convert(tag = "item")
Traceback (most recent call last):
File "", line 1, in 
File "c\Python Folder\xmlutils.py\xmlutils\xml2csv.py",
line 56, in convert
# event, root = self.context.next()
AttributeError: '_IterParseIterator' object has no attribute 'next'

Go to your file location and change the line #event,root=self.context.next() to event, root = self.context.__next__()
