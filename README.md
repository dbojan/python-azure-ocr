

# python-azure-ocr

use azure ocr from python  
#2024-05-18-1  

## setting azure

You can use azure 12 months for free, then you have to pay $1 for 1000
images.  
(20 Images per minute, 5k per month). Using ‘document studio’
Pdfs/Multipage tiffs will only scan 1st image.

Command line version of python-azure-ocr utility does not accept pdfs.

you can use pdf-xchange viewer to convert pdf to images, or command line
(Ghostscript):

`gswin32c.exe -sCompression=pack -dTextAlphaBits=4 -dGraphicsAlphaBits=4  -sDEVICE=tiffgray -r300 -o out-%%03d.tif file.pdf `


You need phone number (not virtual), and credit card number. “Your
credit card will not be charged, or might be charged for $1 for testing
if it real, and $1 will charged back"

If you haven’t already:  
- Create free azure account,  
- using azure web dash board, create a resource:  
- click on +  
- computer vision  
  - subscription: something line Azure subscription  
  - resource group: create new, something like: ocr-test1  
  - region: I selected North EU  
  - name: enter what ever you want  
  - pricing: select free f0 (20 calls per minute, 5k per month)

When you click on you created resurce, you will see your **key(s) and
endpoint.**
You will need **one key**, doesn’t matter which one, and **endpoint**, to use the program.

## setting python

if you haven’t already, install ‘azure-ai-vision-imageanalysis’ using
pip:  
`pip install azure-ai-vision-imageanalysis`

Note: some versions of azure-ocr are not available for free tiers.

## using the program

- download zip, unpack,  
- open azure_ocr.py in notepad++, or notepad,  
- enter your **key and endpoint**  
- put images created from pdf into 'ocr' folder  
- double click “azure_ocr.bat”
