# Default convection
## @resp :  
{...,  
isOk:boolean  
}  

## Message:
{  
    id:string,  
    text:string,  
    date:string  //ISO 8601 format,  
    isRead:boolean //@default  false  
}  

## User:  
{  
  
}  

# Account

##  POST  /login
### @req
{  username:string,  
password:string   }
### @resp:default

##  GET /logout
### @resp:defaulr

# Conversations

## GET /conversations
### @desc: return converstaions(chats) with other users
### @resp: [
    {
        id:string,
        users:[User,User....]
    }
]

## GET /conversations/messages?conId={conversation id}
### @desc: return messages from conversations sorted by date
### @resp:   [
    Message,Message...  
]


# WebSocket

## To server:
### URI message/send
### @desc: Sending message to server using websocket
{  
    conversation:string,  
    message:string  
}
## From server:
### URI message/get
### @desc: Subscribe on getting message to add it dynamicly 
{  
    conversation:string,  
    author:string,  
    date:string  //ISO 8601 format  
}  
