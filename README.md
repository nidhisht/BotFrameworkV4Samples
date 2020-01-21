# Steps to deploy Echo Bot on Azure
Refer [wiki](https://github.com/nidhisht/BotFrameworkV4Samples/wiki/Steps:-Deploy-Echo-Bot-on-Azure) for step by step instructions.

# Chatbot Architecture
<img width="500" alt="Common Bot Architecture" src="https://user-images.githubusercontent.com/42999787/72779441-f6d64600-3c41-11ea-9075-e13c24e9fc84.png">

This chatbot is designed as cloud native application. All the components are deployed on Azure PaaS. Microsoft cognitive services are used for giving intelligence to the chatbot.


# Bot Flow
<img width="520" alt="Common Bot Architecture Flow" src="https://user-images.githubusercontent.com/42999787/72779471-081f5280-3c42-11ea-84cb-4948b96bd504.png">

1. User access the chatbot with web app

2. User is authenticated using Azure Active directory

3. User token information is stored on Azure table storage

4. User sends the utterances to Bot application

5. Spell check of utterance is done through Bing Spell Check

6. Profanity check of utterance is done through Content Moderation Service

7. Natural Language processing is done through LUIS & intents are identified from user utterance

8. QnA Maker stores question & answer pair

9. Once the intents are identified, Corpus Api is invoked from Bot Application. Corpus Api reads corpus from Blob storage and send response back to Bot Application.

10. Corpuses are stored within Azure Blob storage container. 

11. Azure Sql database used for user conversation logging

12. Telemetry is logged in Azure Application Insights
