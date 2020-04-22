# Foobar

DiscordWebhook helps easily integrates in any C# application. It let's you send updates or messages to any discord server (provided you have a webhook url).


## Dependencies
[Json.NET](https://github.com/JamesNK/Newtonsoft.Json)

## Customization
Upon creating the Webhook, you are able to set a default username and avatar that will be used unless specified otherwise when sending a message.

## Example Usage

```cs
var discord = new DiscordWebhook("Link goes here");
var testEmbed = new EmbedBuilder()
    .WithTitle("This is a test embed")
    .AddField("Field 1", "This is some useful text in field 1", false)
    .AddField("Field 2 but inline is enabled", "Hi", true)
    .AddField("Field 3 but it is inline", "im on the right", true)
    .WithAuthor("nikolalv", "https://github.com/nikolalv", "https://avatars3.githubusercontent.com/u/1341206")
    .WithColor(250,0,0)
    .WithTimestamp(DateTime.Now)
    .WithImage("https://avatars3.githubusercontent.com/u/1341206")
    .WithThumbnail("https://pbs.twimg.com/profile_images/1212820842712727552/XCuWn8yF_400x400.jpg");
discord.SendMessageAsync(embeds: testEmbed.Build());
```

![Output](https://i.imgur.com/6O3Zs2D.png)
