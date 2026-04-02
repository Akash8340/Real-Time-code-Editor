# 🧑‍💻 Realtime Collaborative Monaco Editor

A Google-Docs style realtime code editor built with **React + Vite + Monaco Editor + Yjs + Socket.IO**.

Users can join a shared room, edit code together, and see who is online in realtime.

---

## ✨ Features

- ⚡ Realtime collaborative editing (CRDT powered by Yjs)
- 👥 Live presence system (see active users)
- 🔌 WebSocket sync using Socket.IO
- 🧠 Conflict-free editing (no merge conflicts)
- 💻 Monaco Editor (VS Code editor in browser)
- 🌐 Environment-based configuration

---

## 🏗️ Tech Stack

### Frontend
- React (Vite)
- Monaco Editor
- Yjs
- y-socket.io

### Backend
- Node.js
- Socket.IO server for Yjs syncing

---

## 📸 How it Works

1️⃣ User enters a username.

2️⃣ App connects to the Yjs collaboration server using Socket.IO.

3️⃣ All users join the same shared room.

4️⃣ Monaco editor is bound to a shared **Yjs document (CRDT)**.

5️⃣ When a user types:
- Changes are applied locally.
- Yjs converts them into CRDT updates.
- Updates are sent through Socket.IO.
- Other clients receive and apply updates instantly.

6️⃣ The **Yjs Awareness API** tracks active users.
- Each client broadcasts their username.
- Users joining/leaving triggers realtime updates.
- Offline users are automatically removed.

---

### Architecture Overview
