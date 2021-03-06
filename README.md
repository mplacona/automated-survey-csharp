[![Build
status](https://ci.appveyor.com/api/projects/status/6by444f1kiemb7ox/branch/master?svg=true)](https://ci.appveyor.com/project/acamino/automated-survey-csharp/branch/master)

# Automated Surveys using ASP.NET MVC

This application demonstrates how to use Twilio and TwiML to perform automated phone surveys.

## Running locally

The application requirements are minimal, if you have installed [Visual Studio](https://www.visualstudio.com/) you're almost done.

1. Clone the repository.
2. Open the solution file in Visual Studio.
![Open the solution file](https://raw.github.com/TwilioDevEd/automated-survey-csharp/master/solution-file.png)
3. Build the solution.
![Build the solution](https://raw.github.com/TwilioDevEd/automated-survey-csharp/master/build-solution.png)
4. Run `Update-Database` to execute the migrations.
![Run Update-Database](https://raw.github.com/TwilioDevEd/automated-survey-csharp/master/update-database.png)

Running the command `Update-Database` will run the migrations and run the `Seed` method, if you want to inspect this you can inspec SQL Server Object Explorer.

That's it!

## Configuring Twilio to call your application

### Exposing the application using ngrok

For this demo it's necessary that your local application instance is accessible from the Internet. The easiest way to accomplish this during development is using ngrok. The installer and also the installation instructions are available [here](https://ngrok.com/).

Once you have the application running you can expose it to the wider internet by running (port 1302 is the default port for this application)

```
ngrok http 1302 -host-header="localhost:1302"
```

### Configuring Twilio Webhooks

In order to receive incoming calls we need to first configure our [Twilio phone
number](https://www.twilio.com/user/account/phone-numbers/incoming).

![Configure Twilio Phone](https://raw.github.com/TwilioDevEd/automated-survey-csharp/master/configure-twilio-phone.png)

Click on the red number, and then set the Voice Request URL. Don’t forget to
save the changes.

![Set Voice Request URL](https://raw.github.com/TwilioDevEd/automated-survey-csharp/master/set-voice-request-url.png)
