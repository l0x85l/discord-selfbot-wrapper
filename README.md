# discord-selfbot-wrapper
Discord api wrapper for creation of self bots


## Usage

Creating a selfbot

```java
  SelfClient selfClient = new SelfClient("token");
```

An example to print guild, friend, channel stuffs

```java
        List<Guild> guilds = selfClient.guilds();
        List<Friend> friends = selfClient.friends();
        List<Channel> channels = selfClient.channels();
        guilds.forEach(g -> System.out.println("name > " + g.name() + " | " + "id > " + g.id()));
        friends.forEach(f -> System.out.println("name > " + f.username() + " | " + "id > " + f.id()));
        channels.forEach(c -> System.out.println("id > " + c.id() + " | " + "last message id > " + c.last_message_id()));
    }
```

Getting messages

  ```java
        List<Channel> channels = selfClient.channels();
        for(Channel channel : channels) {
            List<Message> messages = selfClient.messages(channel.id());
            for(Message message : messages) {
                System.out.println("content > " + message.content() + " id > " + message.id());
            }
        }
```

or get messages by from channel id

  ```java
        Channel channel = selfClient.channel("channel_id");
        List<Message> messages = selfClient.messages(channel.id());
        for(Message message : messages) {
            System.out.println("content > " + message.content() + " id > " + message.id());
        }
```

Changing theme/locale

  ```java
     selfClient.change_theme(SelfClient.Theme.LIGHT); //SelfCLient.Theme.DARK
     selfClient.change_locale(SelfClient.Locale.THAI); //SelfClient.Locale.GREEK/JAPAN/BULGARIAN/RUSSIAN
```

Changing status/bio

  ```java
     selfClient.change_status("hello world");
     selfClient.change_bio("im gay");
```

Changing avatar and reset

  ```java
     selfClient.change_avatar();
     selfClient.reset_avatar();
```

Creating/leaving/joining/deleting guild

  ```java
     selfClient.create_guild("guild name");
     selfClient.leave_guild("guild id");
     selfClient.join_guild("invite code");
     selfClient.delete_guild("guild id");
```

Add/delete/block friend
  ```java
     selfClient.add_friend("name", "discriminator);
     selfClient.delete_friend("friend id");
     selfClient.block_friend("friend id");
```



