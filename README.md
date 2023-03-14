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
