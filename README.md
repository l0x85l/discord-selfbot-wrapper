# discord-selfbot-wrapper
Discord api wrapper for creation of self bots


## Usage

Creating a selfbot

```java
  SelfClient selfClient = new SelfClient("token");
```

An example to list all guilds

```java
   List<Guild> guilds = selfClient.guilds();
        for(Guild guild : guilds) {
            System.out.println("name: " + guild.name() + " | id: " + guild.id());
        }
```
