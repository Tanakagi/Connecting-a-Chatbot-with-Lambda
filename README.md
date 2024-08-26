# Connecting-a-Chatbot-with-Lambda

In this project I created a  chatbot named BankerBot that could help my imaginary bank's customers check their account balance between accounts. I connected the chatbot to Amazon Lambda to return a balance to my customers.

## AWS services used:
**• Amazon Lex** - used to create my chatbot named BankerBot.

**• AWS Lambda**: - used to return a random bank balance to my imaginary bank's customers between their accounts.

## Task list:

- create a new Lex chatbot called BankerBot.
  
- Set up WelcomeIntent.
  
- Set up customised FallbackIntent.
  
- CheckBalance set up with a custom slot type called accountType.


# Project walk-through:

### Task 1: Creating the Lex chatbot.

• I Navigated to Amazon Lex.
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />


• I then started with the creation of my chat Bot and configured it as follows:
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />


<b>• Under IAM permissions, I selected Create a role with basic Amazon Lex permissions.</br>
<b>That I used to call another service called Lambda later in this project, and configured the rest as follows:</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />


<b>•  For Intent classification confidence score threshold, I kept the default value of 0.40, so that my chatbot needs</br> 
<b>to be at least 40% confident that it understands what the user is asking to be able to give a response.</br>
<b>•I then clicked done.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />


• I navigated to my Chatbot named BankerBot and configured the Intent name as follows:
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I then scrolled down to the Sample utterances panel.</br>
<b>•selected Plain Text.</br>
<b>• Then entered the following, which represented the user inputs (called utterances) that will trigger this intent:</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I scroll down to Closing response, and expand the speech bubble for Response sent to the user after the intent is fulfilled.</br>
<b>• In the Message field, I entered the message: `Hi! I'm BB, the Banking Bot. How can I help you today?`</br>
• then clicked Save intent and Build.
</br>
</br>

### Task 2: Testing
<b>• In this task I began testing the chatbot.</br>
<b>• In the dialogue pop-up, I interacted with the bot by entering opening message, as a way to check that I’ve set up the chatbot without any errors:</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I then started to Manage the FallbackIntent so that the fallback intent would sound more human-like.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I opened the toggle labelled Variations - optional.</br>
<b>• I Entered the following text, then clicked update response.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I then saved and built the changes and began the 2nd round of testing.</br>
<b>• I tested the message that failed on my last try. The chatbot returned the closing response message I added in the previous step.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
</br>
</br>

 ### Task 3: Creating the accountType Custom Slot

<b>• I then Created the accountType Custom Slot are pieces of information that a chatbot needs to complete a user's request.</br>
<b>• Then Added a blank slot type.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• This brought up a large Slot types editor pane, which I configured as follows:</br>
<b>• then Saved the slot type.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
</br>
</br>

 ### Task 4: Create the CheckBalance intent

<b>• I went back to Intents.</br>
<b>• selected Add intent, then clicked Add empty intent. Then configured the following:</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I scrolled down to Sample utterances and switched to Plain Text then added the following:</br>
<b>• This prepares Amazon Lex to look for the slot values from the user's input. Lex will automatically fill in that</br>
<b>information and won't need to prompt the user for their accountType anymore, saving time for the user.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

• I scrolled down to the Slots pane and added the following slot.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

• I then did the same for a date of birth slot type.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I then clicked Save intent and Build to save the changes</br>
<b>• I then started the 3rd round of testing the chatbot.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I then clicked Inspect to validate that my chatbot was set up correctly. Which it was since Amazon Lex only prompted users</br>
<b>• for the date of birth, as it already knows that it should be the Savings account it checks.</br>
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
</br>
</br>

 ### Task 5: Updat the chatbot to Define an AWS Lambda function that will get a user's balance.

**In this task I did the following:**

<b>• Defined an AWS Lambda function that will get a user's balance.</br>
<b>• Connected my AWS Lambda function with your Amazon Lex chatbot.</br>
<b>• Connected my CheckBalance intent with the Lambda function.</br>

• I stated by creating the Lambda Function and configured it as follows:
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

• I Navigated to Amazon Lex.
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

• I Navigated to Amazon Lex.
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

• I Navigated to Amazon Lex.
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />
• I Navigated to Amazon Lex.
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

• I Navigated to Amazon Lex.
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

• I Navigated to Amazon Lex.
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

### Front-end




## Goal

The goal is to get hands-on with DevOps practices like Containerization, CICD and monitoring.

Look at the capstone project for more detials.


## License

[MIT](./LICENSE)
