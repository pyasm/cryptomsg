# cryptomsg
messaging system using a key per discussion shared by members only

# server
the server transmits messages to the members

# clients
when a client `creator` creates a room it creates a key which is encrypted using the client key and sent to the server
when a new client `joinee 1` connects he sends his public key to `creator` which sends back the encrypted room key
Then any new `joinee N` can join the room by asking any member

# send a message
when an `author` sends a message :  
1. `author` encrypts the message using the room key  
2. the encrypted message is sent to all connected `members` of the room

# leaving a room
when a `member` leaves a room a new room key is created by the oldest member of the room then sent to all the remaining members

# concurency
if a message arrives to the room with the wrong key it's droped and the client must send a new one
