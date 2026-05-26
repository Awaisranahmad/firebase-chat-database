## Queries Practiced – Firestore Console

## Query 1: Online Users
javascript
where('isOnline', '==', true)
Result: Users with isOnline: true

Query 2: Age > 22
javascript
where('age', '>', 22)
Result: Ali (25), Zainab (30), etc.

Query 3: Age Descending (Top 5)
javascript
orderBy('age', 'descending')
limit(5)
Result: Oldest 5 users first

Query 4: Urdu Speakers by Age
javascript
where('language', '==', 'Urdu')
orderBy('age', 'ascending')
Result: Rana Awais (22) → Ali (25)

Query 5: MessagesCount >= 100
javascript
where('messagesCount', '>=', 100)
Result: Ali (156), Fatima (342), Zainab (567)

Query 6: Online Users from Multan
javascript
where('isOnline', '==', true)
where('city', '==', 'Multan')
Result: Rana Awais (needs composite index)

Query 7: Recent 2 Messages
javascript
collection('messages')
orderBy('timestamp', 'descending')
limit(2)
Result: Latest 2 messages

Query 8: Non-Group Chats
javascript
collection('chats')
where('isGroup', '==', false)
Result: Both private chats (Ali-Fatima, Ali-Ahmed)

Composite Indexes Created
language (asc) + age (asc)

age (asc) + messagesCount (asc)
