# AI Bot with human handoff capabilities 

Bot Framework v4 skills echo sample.

This bot has been created using [Bot Framework](https://dev.botframework.com). The root bot has human handoff capabilities. you can also connect it to a skill bot that has multiturn QNA based dialogues.

## Prerequisites

- [.NET Core ](https://dotnet.microsoft.com/en-us/download)
- [Visual Studio](https://visualstudio.microsoft.com/downloads/)
- [Bot Framework Emulator](https://github.com/microsoft/botframework-emulator)

  ```bash
  # determine dotnet version
  dotnet --version
  ```

## Key concepts in this sample

The solution contains a bot with waterfall dialog, multiturn QNA dialog, prompt dialog and human-agent routing component.



## To try this sample

- Clone the repository

    ```bash
    git clone --single-branch --branch staging https://github.com/sou-project/azure-chatbot
    ```
- Open Visual Studio, 
- In Visual Studio, open the bot project
- Run the project without Debugging, `Run` -> `Start Without Debugging`

![Start Without Debugging](/Images/RunWithoutDebugging.png)

## Testing the bot using Bot Framework Emulator

[Bot Framework Emulator](https://github.com/microsoft/botframework-emulator) is a desktop application that allows bot developers to test and debug their bots on localhost or running remotely through a tunnel.


### Test the bot using Bot Framework Emulator

- Launch Bot Framework Emulator
- File -> Open Bot
- Enter a Bot URL of `http://localhost:3978/api/messages`, and input `MicrosoftAppId` and `MicrosoftAppPassword` from  [appsetting.json](https://github.com/sou-project/azure-chatbot/blob/staging/appsettings.json)

## Deploying on Azure
- In Visual Studio , `Project` -> `Restore Nuget Packages`
- `Build` -> `Clean All`
- `Build` -> `Rebuild All`
- ![Clean and Rebuild](/Images/CleanRebuild.png)
- `Visual Studio` -> `Accounts` -> Add you Microsoft Azure Account
- ![Create Account 1](/Images/CreateAccount1.png)
- ![Create Account 2](/Images/CreateAccount2.png)
- `Build` -> `Publish` -> `Refresh` -> Choose the App Service in which you want to publish the bot -> `Publish`<br>
In the case of Staging Enviroment Tenant 1, use stgTenant1Bot App Service in stg_testTenant1 Resource Group
-  ![Publish](/Images/Publish.png)
