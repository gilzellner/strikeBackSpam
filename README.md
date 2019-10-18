Join the [dev chat on Whatsapp](https://chat.whatsapp.com/JHQJK33hxvNFhvGcuOmDkp)

# Spec
An app (iphone+android) where users can easily report an SMS message as “Election spam”, and indicate the relevant party. When a user does this, a counter SMS is sent to the party leaders / knesset members from the user’s own device.

The app will also maintain a list of known spam messages (by content?), and auto-detect spam which is similar to spam reported by other users. When such messages are auto-detected as spam (let’s say marked as spam by more than X users), any similar future messages received by other users also cause a counter SMS to be sent to the relevant party leaders.

# Design
services:
Receiver: Receive spam alert from users. Automated or manual, initiated from user devices. (Golang?)
	This endpoint receives post requests from clients with the spam message, source number and additional info. Json from user, sends json to (2).

Aggregator logger: logs spam messages in db (Python?)
Receives messages from (1), inserts into db (elastic?)	

Response activator: generates messages to be sent and puts them in send queue to (4)
Matches to relevant politician and party lead as well.(Python?)
Gets politician info from db (mysql?)	

Sender: sends messages via client devices (Python and store in Firebase?)

# Open Issues
https://github.com/gilzellner/strikeBackSpam/issues



