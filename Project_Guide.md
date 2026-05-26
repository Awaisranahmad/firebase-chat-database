# Project Guide – WhatsApp-like Firestore Database

## Database Structure

### users Collection (6 documents)
Fields: name, email, phone, status, lastSeen, isOnline, city, age, joinedDate, messagesCount, language, profilePic, bio, contacts

### messages Collection (3 documents)
Fields: senderId, receiverId, senderName, receiverName, text, timestamp, isRead, messageType, reaction (map), isEdited, editedAt, mediaUrl

### chats Collection (2 documents)
Fields: participants (array), participantNames (array), lastMessage, lastMessageTime, unreadCount (map), isGroup

## Why This Design?
- **participants array** – allows `array-contains` query to find all chats of a user
- **participantNames array** – denormalization to avoid extra user lookups
- **unreadCount map** – per-user unread counts in a single field
- **lastMessage/time** – duplicates for fast chat list display

## Indexes Created
1. language (asc) + age (asc) – for query: `language == "Urdu" AND age > 23`
2. age (asc) + messagesCount (asc) – for query: `age > 20 AND messagesCount > 100`

## Authentication
- Method: Email/Password
- Test users: ali@chatapp.com, fatima@chatapp.com, awais@chatapp.com

## Security Rules Summary
- Users: anyone can read, only owner can write
- Messages: only sender/receiver can read/write
- Chats: participants can read
