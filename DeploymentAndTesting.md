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
- Use value for ConnectionString as ```Endpoint=https://config-ai-dev-helpmeee-jp.azconfig.io;Id=vwv+-ld-s0:RNf4C4AESK1X9Vx43tEY;Secret=ko3Vr+nyLvFIhNUUN4e9E+s0eadgKHcdPVJ+5jfomRM=```

    ```bash
    git clone --single-branch --branch staging https://github.com/sou-project/azure-chatbot
    ```
1. ```cd azure-chatbot```
5. ```dotnet run```
### Or you can also open and run the bot in Visual Studio. You would stil need to do steps 1-4 before on the terminal before you run in Visual Studio


## Testing the bot using Bot Framework Emulator

[Bot Framework Emulator](https://github.com/microsoft/botframework-emulator) is a desktop application that allows bot developers to test and debug their bots on localhost or running remotely through a tunnel.


### Test the bot using Bot Framework Emulator

- Launch Bot Framework Emulator
- File -> Open Bot
- Enter a Bot URL of `http://localhost:3978/api/messages`, and input `MicrosoftAppId` and `MicrosoftAppPassword` from  [appsetting.json](/appsettings.json)
