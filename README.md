

# python-azure-ocr

use azure ocr from python  
#2024-05-18-1  

## setting azure

You can use azure 12 months for free, then you have to pay $1 for 1000
images. You **must move to** pay as you go (basic supscription - $0) after first month. Be careful not to go over free amount of units. *

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
- Create free azure account  
- go to https://portal.azure.com/#home
- click on computer vision on the left
- click on + to create new resource in "computer vision"  
  - subscription: something like Azure subscription  
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


*Note:  
https://azure.microsoft.com/en-us/free/free-account-faq  
How do I get popular services free for 12 months?  

When you create your Azure free account, you start getting monthly free amounts of certain types of services. **If you move to pay-as-you-go pricing** within 30 days or after you’ve used your credit, you’ll continue to receive monthly free amounts of popular services until 12 months after you created your account. After that, if you’re using any of these services, they’ll continue to run and you’ll be billed for them at pay-as-you-go rates.



https://azure.microsoft.com/en-us/pricing/free-services#richtext-oc4492  

12 months free services is available only to new customers who have not previously had an Azure account or received 12 months of free services. It is not currently available to customers who sign up directly for pay as you go in China and India. Customers who try Azure free **must move to pay as you go** within 30 days to continue receiving 12 months free services.


more info here:  
https://azure.microsoft.com/en-us/free/free-account-faq/  
https://learn.microsoft.com/en-us/azure/cost-management-billing/manage/avoid-charges-free-account  
https://learn.microsoft.com/en-us/azure/cost-management-billing/manage/check-free-service-usage  

relevant services:  
https://azure.microsoft.com/en-us/pricing/free-services#richtext-oc4492  

|Azure service|Description|Type|Free monthly amount|Free period 
|---|---|---|----|---
|*Computer Vision|Extract rich information from images to categorize and process visual data.|	|5,000 transactions for each S1, S2, and S3 tier|12 months 
|Speaker Recognition|Accurately verify and identify speakers by their unique voice characteristics.|AI + machine learning|10,000 transactions each of speaker verification, speaker identification, and voice storage|Always
|*Speech to Text|Transcribe spoken audio to text.|AI + machine learning|5 audio hours each of Standard, Custom, and Conversation Transcription Multichannel Audio, 1 Custom endpoint hosting model|Always 
|Speech Translation|Integrate real-time speech translation into your app.|AI + machine learning|5 audio hours Standard|Always 
|*Text to Speech|Build apps that convert text to lifelike speech.|AI + machine learning|5 million characters Standard, 500,000 characters Neural, and hosting model|Always 
|Azure AI Document Intelligence (old?)|Automate the extraction of text, key/value pairs, and tables from your documents.|AI + machine learning|500 pages S0 tier|12 months


