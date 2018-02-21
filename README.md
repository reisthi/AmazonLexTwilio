# Amazon-lex-twilio-integration ![CI status](https://img.shields.io/badge/build-passing-brightgreen.svg)

An AWS Lambda function that integrates Twilio Programmable SMS with Amazon Lex.

For detailed implementation instructions, please read this [this AWS blogpost](https://aws.amazon.com/blogs/ai/integrate-your-amazon-lex-bot-with-any-messaging-service/)

## Requirements
* AWS account along with sufficient permissions to modify or create an AWS IAM, Lex, and Lambda.
* Twilio SMS-enabled phone number. 
* A Lex Bot. Don't have one yet? No worries! You can use one of the samples offered by AWS. To learn how to create one [click here](https://docs.aws.amazon.com/lex/latest/dg/gs-bp-create-bot.html).
* An IAM Role that allows the interactions with your Lex Bot. 

## Integration
### Step 1 - Get Twilio's Credentials
Go to your Twilio account. On your **Console Dashboard**, click on **Settings** and then **General**. Record the **Account SID** and the **AUTH Token** numbers, you will need it later. OBS: Mine only worked with LIVE Credentials but you can try the TEST Credentials to see if integrates.  
### Step 2 - Integrate Lex 
Make sure your Bot is working accordingly by using the test chatbot located on the right side of your Amazon Lex Console.
1. Go to **Channels**
2. Select **Twilio SMS**
3. Chose a **Channel Name**. Ex:  *TwilioLexBot*.
4. An **IAM Role** should appear automatically.
5. For **KMS Key** chose *aws/lex*
6. Chose your **Alias**. (Publish your Bot if you don't have one)
7. For **Authentication Token** and **Account SID**, type the recorded ACCOUNT SID and the AUTH TOKEN.
8. Click **Activate** and copy the **Endpoint URL** that was generated.
### Step 3 - Finish up Integration on Twilio
1. Go back to Twilio and then go to **Phone Numbers/ Manage Numbers/** and select the number you are testing. 
2. Scroll down to **Messaging** and chose *Webhooks, TwiML Bins, Functions, Studio, or Proxy* for *CONFIGURE WITH*.
3. For **A MESSAGE COMES IN**, chose *Webhook* and paste the copied URL.
4. Test your bot
