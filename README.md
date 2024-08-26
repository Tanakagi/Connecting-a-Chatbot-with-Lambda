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
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%201.png" height="80%" width="80%" />
</br>
</br>

• I then started with the creation of my chat Bot and configured it as follows:
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%202.png" height="80%" width="80%" />
</br>
</br>

<b>• Under IAM permissions, I selected Create a role with basic Amazon Lex permissions.</br>
<b>That I used to call another service called Lambda later in this project, and configured the rest as follows:</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%203.png" height="80%" width="80%" />
</br>
</br>

<b>•  For Intent classification confidence score threshold, I kept the default value of 0.40, so that my chatbot needs</br> 
<b>to be at least 40% confident that it understands what the user is asking to be able to give a response.</br>
<b>•I then clicked done.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%204.png" height="80%" width="80%" />
</br>
</br>

• I navigated to my Chatbot named BankerBot and configured the Intent name as follows:
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%205.png" height="80%" width="80%" />
</br>
</br>

<b>• I then scrolled down to the Sample utterances panel.</br>
<b>•selected Plain Text.</br>
<b>• Then entered the following, which represented the user inputs (called utterances) that will trigger this intent:</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%206.png" height="80%" width="80%" />
</br>
</br>

<b>• I scroll down to Closing response, and expand the speech bubble for Response sent to the user after the intent is fulfilled.</br>
<b>• In the Message field, I entered the message: `Hi! I'm BB, the Banking Bot. How can I help you today?`</br>
• then clicked Save intent and Build.
</br>
</br>

### Task 2: Testing
<b>• In this task I began testing the chatbot.</br>
<b>• In the dialogue pop-up, I interacted with the bot by entering opening message, as a way to check that I’ve set up the chatbot without any errors:</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%207.png" height="50%" width="50%" />
</br>
</br>

<b>• I then started to Manage the FallbackIntent so that the fallback intent would sound more human-like.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%208.png" height="80%" width="80%" />
</br>
</br>

<b>• I opened the toggle labelled Variations - optional.</br>
<b>• I Entered the following text, then clicked update response.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%209.png" height="80%" width="80%" />
</br>
</br>

<b>• I then saved and built the changes and began the 2nd round of testing.</br>
<b>• I tested the message that failed on my last try. The chatbot returned the closing response message I added in the previous step.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/1cd3d583878c9ddb22ae08fe230aca4e13bc909a/Project%20Images/Image%2010.png" height="50%" width="50%" />
</br>
</br>
</br>

 ### Task 3: Creating the accountType Custom Slot

<b>• I then Created the accountType Custom Slot are pieces of information that a chatbot needs to complete a user's request.</br>
<b>• Then Added a blank slot type.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2011.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2012.png" height="80%" width="80%" />
</br>
</br>

<b>• This brought up a large Slot types editor pane, which I configured as follows:</br>
<b>• then Saved the slot type.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2013.png" height="80%" width="80%" />
</br>
</br>
</br>

 ### Task 4: Create the CheckBalance intent

<b>• I went back to Intents.</br>
<b>• selected Add intent, then clicked Add empty intent. Then configured the following:</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2014.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2015.png" height="80%" width="80%" />
</br>
</br>

<b>• I scrolled down to Sample utterances and switched to Plain Text then added the following:</br>
<b>• This prepares Amazon Lex to look for the slot values from the user's input. Lex will automatically fill in that</br>
<b>information and won't need to prompt the user for their accountType anymore, saving time for the user.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2016.png" height="80%" width="80%" />
</br>
</br>

• I scrolled down to the Slots pane and added the following slot.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2017.png" height="80%" width="80%" />
</br>
</br>

• I then did the same for a date of birth slot type.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2018.png" height="80%" width="80%" />
</br>
</br>

<b>• I then clicked Save intent and Build to save the changes</br>
<b>• I then started the 3rd round of testing the chatbot.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2019.png" height="50%" width="50%" />
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2020.png" height="50%" width="50%" />
</br>
</br>

<b>• I then clicked Inspect to validate that my chatbot was set up correctly. Which it was since Amazon Lex only prompted users</br>
<b>• for the date of birth, as it already knows that it should be the Savings account it checks.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2021.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2022.png" height="80%" width="80%" />
</br>
</br>
</br>

 ### Task 5: Updat the chatbot to Define an AWS Lambda function that will get a user's balance.

**In this task I did the following:**

<b>• Defined an AWS Lambda function that will get a user's balance.</br>
<b>• Connected my AWS Lambda function with your Amazon Lex chatbot.</br>
<b>• Connected my CheckBalance intent with the Lambda function.</br>

• I started by creating the Lambda Function and configured it as follows:
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2023.png" height="80%" width="80%" />
</br>
</br>

<b>• Once the Lambda function was created I scrolled down to the Function code section and added the following Python script.</br>
<b>• This Python script gives a random amount when the chatbot requests the account balance from a user, but in a real-life scenario,</br>
<b> I would configure lambda to connect through a database and look for a specific user's account balance.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2025.png" height="80%" width="80%" />
</br>
</br>

<b>**I then Connected AWS Lambda with Amazon Lex**</br>
<b>• I went back to the Amazon Lex console and selected BankerBot.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2026.png" height="80%" width="80%" />
</br>
</br>

<b>• I then clicked Aliases On the left-hand menu then selected the default TestBotAlias.</br>
<b>• The TestBotAlias is a default version of your bot that's made for testing or development.</br>
<b>• and associated the Lambda function to this TestBotAlias version of your bot.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2027.png" height="80%" width="80%" />
</br>
</br>
</br>

 **I then Connected my CheckBalance intent with my Lambda function**.
<b>The Lambda function was ready to work on the BankingBot intents, but I still needed to tell Amazon Lex which intent would use the Lambda function.</br>

<b>• I navigated to my CheckBalance intent and scrolled down to the Fulfilment panel.</br>
<b>• Expanded the On successful fulfilment bubble.</br>
<b>• and selected Advanced options.</br>
<b>• Under the Fulfilment Lambda code hook panel, I clicked the checkbox next to Use a Lambda function for fulfilment.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2028.png" height="80%" width="80%" />
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2029.png" height="80%" width="80%" />
</br>
</br>

<b>• I then clicked Update options, Save intent and Build and started the 4th round of testing.</br>
<b>• I Asked for the balance of my savings accounts and the bot was able to return (a random) bank balance figures.</br>
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2030.png" height="50%" width="50%" />
<img src="https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/da8cecc7d3ce5311e2af3ee2b1999acbe2aea61c/Project%20Images/Image%2031.png" height="50%" width="50%" />
</br>

## End of project.

This was the end of the project since I was able to successfully create a  chatbot named BankerBot that could help my imaginary bank's customers check their account balance between accounts.


## Lambda function

[Chatbot Lambda Function code](https://github.com/Tanakagi/Connecting-a-Chatbot-with-Lambda/blob/5fea96b1e260af44cb17f4362e629bda4eb129ca/Chatbot%20Lambda%20Function%20code.py)
