# Command-System
Minecraft 1.8.9 based like bukkit command system

# Setup
go to ``EntityPlayerSP`` class and change ``sendChatMessage`` method to;
```
public void sendChatMessage(String message) {
	   if (CommandManager.isCommand(message)) {
		   final Command cmd = CommandManager.findCommand(message);
		   if (cmd.getExecutor() != null){
			   cmd.getExecutor().execute(this, CommandManager.getArgs(message));
		   }
	   } else {
		   this.sendQueue.addToSendQueue(new C01PacketChatMessage(message));
	   }
   }
   ```
   
   then go your main class and put your initialize method;
   ``
   CommandManager.loadCommands();
   ``
   
   # Credits
   thanks for the args [Shiryu](https://github.com/Sh1ry "Heading link")
   
