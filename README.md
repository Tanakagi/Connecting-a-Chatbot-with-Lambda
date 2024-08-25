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


• I navigated to my Chat bot named BankerBot and configured the Intent name as follows:
<img src="https://github.com/Tanakagi/Cloud-Security-with-AWS-IAM/blob/88ce441e5b1ce7ee19f5121d70bc3262df613f17/Project%20images/image%201.png" height="80%" width="80%" />

<b>• I then scrolled down to the Sample utterances panel.</br>
<b>•selected Plain Text.</br>
<b>• Then entered the following, which represented the user inputs (called utterances) that will trigger this intent:</br>
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
