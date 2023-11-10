# ---


<tt>
#@title <center>𝙋𝙮𝙧𝙤𝙜𝙧𝙖𝙢 𝙎𝙚𝙨𝙨𝙞𝙤𝙣</center>

#@markdown ---

API_KEY = 0 #@param {type:"integer"}
API_HASH = "" #@param {type:"string"}
Pyrogram_Version = "2.0.106" #@param ["2.0.66", "2.0.77", "2.0.88", "2.0.106"] {allow-input: true, type:"string"}

#@markdown ---

!pip3 install tgcrypto pyrogram==$Pyrogram_Version

from pyrogram import Client
from pyrogram.errors import UserIsBot

async with Client(name="WZ-User", api_id=API_KEY, api_hash=API_HASH, in_memory=True) as app:
    sess = await app.export_session_string()
    print("\nProcessing...")
    donestr = "sent to Saved Messages !!"
    try:
        await app.send_message(
            "me",
            f"#WZMLX #PYROGRAM_SESSION_{Pyrogram_Version}\n\n<code>{sess}</code>",
        )
    except UserIsBot:
        donestr = "Successfully Printed !!"
        print("#WZMLX #PYROGRAM_SESSION_{Pyrogram_Version}")
        print(sess)
    print(f"Done !!, String Session has been {donestr}")
</tt>
