# CoreX.Extensions.Logging
A suitable logging for microservices scenarios, where you need to track logs without sacrificing performance or storage. 

## Getting started
In startup.cs:
```
// ConfigureServices
services.AddHttpLog(Configuration);

// Configure, right before UseMVC
app.UseHttpLog();
app.UseMvc();
```

Then browse your app /log to view a realtime console view of your application!

### Configurations 
In appsettings.json put the following section to be able to configure the middleware:
```
  "HttpLogger": {
    "Enabled": true,
    "TimestampFormat": "hh:mm:ss.fff",
    "AllowForAnonymous": true,
    "AllowForUser": "",
    "AllowForRole": ""
  },
```

## /log query options
Browsing the /log url allows you to display filtered logs by certain parameters. Like the following examples:

Display only warnings
```
/log?level=warning
```

Display only my logs: uses cookies to display logs coming only from my browser
```
/log?my
```

