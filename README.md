- š Hi, Iām @dem1se1
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
dem1se1/dem1se1 is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import discord

TOKEN = ""      # Put your Bot token here
SKIP_BOTS = False


client = discord.Client()

@client.event
async def on_ready():
    print('Logged in!')
    for member in client.get_all_members():
        if member.bot and SKIP_BOTS:
            continue
        await member.ban(reason="Banned by BanBot", delete_message_days=7)
        print(f"Banned {member.display_name}!")
    print("Banning is complete!")

client.run(TOKEN)
