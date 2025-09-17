# python-azure-ocr

2025-09-17-1

### What is it:

Command line tool to use ocr from azure cloud. You need free azure account, and python.

You can use azure 12 months for free, then you have to pay $1 for 1000 images. You **must move to** pay as you go (basic supscription - $0) after first month, or it will not work after month. Be careful not to go over free amount of units.

(With regards to pages, azure ai vision(ocrv1), can ocr max in 20 Images per minute, 5k per month for free tier). 

### How to use it:

Right click [here](https://raw.githubusercontent.com/dbojan/python-azure-ocr/refs/heads/main/azure_ocr.zip), select save link as, uncompress.

Put pdf file in 'ocr' folder, click on '_zocr_files_in_ocr_folder.bat', (the last file in folder).


## setting azure v1 (no tables, cheaper)

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

## setting python v1 (no tables, cheaper)

if you haven’t already, install ‘azure-ai-vision-imageanalysis’ using
pip:  
`pip install -U azure-ai-vision-imageanalysis`

Note: some versions of azure-ocr are not available for free tiers.

## setting azure v2 (tables, more expensive)

`pip install -U azure-ai-documentintelligence`  
- on azure ocr portal create "document inteligence" resource. Location: north eu, tier: free  
  
there are two models:
- prebuilt-read, which is cheaper, does not recognize tables, and has **worse** ocr recognition  
- prebuilt-layout, more expensive, better ocr of characters than prebulit-layout, recognizes tables  

choose model by editinig "azure2_ocr.py", and setting var st_model= to prebulit-read, or prebuilt-layout

## using the program

- download zip, unpack,  
- open azure_ocr.py in notepad++, or notepad,  
- enter your **key and endpoint**  
- put images created from pdf into 'ocr' folder  
- double click “azure1_ocr.bat”, or "azure2_ocr.bat"  
  (azure 2 lines output to output.txt could use improvement, though)

*Note:  

What happens after I upgrade?  
You get 12 months of popular services for free, plus more
than 25 products that are always free. Beyond what's free, you
pay only for what you use each month and you can cancel any
time!

What happens to the Azure credit if I upgrade before 30 days?  
Your remaining credit will still be available for the full 30 days
after you started your Azure free account.

Do I have to pay after I upgrade?  
As long as you use the the product quantities that are
included for free, you won't have to pay anything.

What happens with my products if I do not upgrade?  
If you don't upgrade by the end of 30 days or before you've
used your Azure credit (whichever occurs first), you won't be
able to access any Azure services.





https://azure.microsoft.com/en-us/free/free-account-faq  
How do I get popular services free for 12 months?  

When you create your Azure free account, you start getting monthly free amounts of certain types of services. **If you move to pay-as-you-go pricing** within 30 days or after you’ve used your credit, you’ll continue to receive monthly free amounts of popular services until 12 months after you created your account. After that, if you’re using any of these services, they’ll continue to run and you’ll be billed for them at pay-as-you-go rates.



https://azure.microsoft.com/en-us/pricing/free-services#richtext-oc4492  

12 months free services is available only to new customers who have not previously had an Azure account or received 12 months of free services. It is not currently available to customers who sign up directly for pay as you go in China and India. Customers who try Azure free **must move to pay as you go** within 30 days to continue receiving 12 months free services.


https://learn.microsoft.com/en-us/azure/ai-services/translator/translator-faq  
**Each translation counts as a separate translation**


more info here MS:  
https://azure.microsoft.com/en-us/free/free-account-faq/  
https://learn.microsoft.com/en-us/azure/cost-management-billing/manage/avoid-charges-free-account  
https://learn.microsoft.com/en-us/azure/cost-management-billing/manage/check-free-service-usage  
https://learn.microsoft.com/en-us/azure/cost-management-billing/manage/upgrade-azure-subscription  

pricing, after free:  
https://azure.microsoft.com/en-us/pricing/details/ai-document-intelligence/ (prebuilt-model is more expensive than prebuilt-read)  
https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/model-overview (v4, prebuilt-model has tables, prebuilt-read does not)  

https://azure.microsoft.com/en-us/pricing/details/cognitive-services/computer-vision/ (old, no tables recognition)  


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
|*Azure AI Translator |Add real-time, multi-language text translation to your apps, websites, and tools. |AI + machine learning |2 million characters S0 tier |12 months 


-2025-09-17-09  
added v2, which uses two possible models, prebuilt-layout and prebuilt-read  
prebuilt-layout (default) recognizes tables.  
v2 uses document intelligence. 
v1 (previous version) uses ai vision  

-2025-09-09-1  
small update to web page, added some links

-2025-08-03-1  
small updates, use -U to update python lib

-2024-08-05-1
replace dot with newline  

-2024-06-30-1  
use azure ocr from python  

2024-06-26-1 changes  
-now with linux support. open .py in text editor for more info.
