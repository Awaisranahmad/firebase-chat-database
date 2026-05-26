# Firebase Chat App Database – Week 1 Project

## Overview
Complete Firestore database design for a WhatsApp-like chat application.

## Collections Created
- **users** (6 documents) – user profiles with name, email, age, city, online status, etc.
- **messages** (3 documents) – messages with sender/receiver names, timestamps, read status
- **chats** (2 documents) – conversation metadata with participants, last message, unread counts

## Key Features
- NoSQL database design
- CRUD operations via Firebase Console
- Compound queries with composite indexes
- Denormalization for performance (participantNames stored in chats)
- Authentication (Email/Password)
- Security rules (public read for users, private for messages)

## How to View
1. Firebase Console: https://console.firebase.google.com
2. Open project: `chat_app_month1`
3. Firestore Database → browse collections

## Screenshots
See `SCREENSHOTS/` folder

## Security Rules
See `SECURITY_RULES.txt`

## Queries Practiced
See `QUERIES.md`

## Next Steps
- Week 2: Node.js backend
- Week 4: Flutter integration

---
**Status:** Week 1 Complete ✅
