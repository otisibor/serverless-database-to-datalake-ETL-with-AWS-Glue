# Module 3: Build a chatbot in Amazon Lex and handle informational queries

In this module you will build a chatbot in Lex and enable it to answer customer's questions on the offerings of your company. 

At completion of this module you will be able to test out your chatbot in the Lex console by asking questions such as "*Tell me about international plans in Germany.*"

##  Informational queries and chatbots
The first intent you will configure your bot to understand and fulfill will allow your customers to query phone plan options when they travel abroad. This serves an example for a common use case for chatbots: asking information. 

There are two ways you can implement an informational intent: you can make it general or personalize it based on the customer. The latter one requires your bot to be able to identity the customer the bot is interacting with. 

For example, if you build a chatbot that can handle checking the flight status, the general implementation can handle questions like "*what's the status for flight 123?*"; whereas if you can identify the customer asking the question, the bot can give answers to questions to "*what's the status for* ***my*** *flight today?*"

In later modules, you will try out ways for identifying the customer in a Lex bot conversation. For this module, we will stick with a general information query: what are the available phone plan options for a given country the customer is traveling to? The bot will give the same answer for anybody that asks the same question. 



## Implementation Instructions

Each of the following sections provide an implementation overview and detailed, step-by-step instructions. The overview should provide enough context for you to complete the implementation if you're already familiar with the AWS Management Console or you want to explore the services yourself without following a walkthrough.
