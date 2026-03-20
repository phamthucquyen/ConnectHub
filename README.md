# 💬 ConnectHub

ConnectHub is a lightweight terminal-based chat application built with Python sockets and threading.  
It supports a shared community chat room, basic private messaging, and nickname-based user sessions.

## 🚀 Features

- 🛰️ Real-time group chat over TCP sockets
- 👥 Multi-client support with Python threading
- 🏷️ Nickname handshake on connect
- 🔐 Password gate before joining (`1234` in current implementation)
- 📋 List active users with `lst_ppl`
- 📩 Send private messages with `private <nickname> <message>`

## 🛠️ Tech Stack

- Python 3
- `socket` (network communication)
- `threading` (concurrent client handling)

## 📂 Project Structure

```bash
ConnectHub/
├── client.py   
├── server.py  
└── README.md
```

## ⚙️ How It Works

1. Start the server on `localhost:5551`.
2. A client connects and sends:
   - nickname (`NICK` prompt)
   - password (`PASS` prompt)
3. If password matches, the user joins the main chat.
4. Messages are handled in separate threads so multiple users can chat concurrently.

## 🧪 Setup and Run

### 1. ✅ Prerequisites

- Python 3 installed

### 2. 🖥️ Start the server

```bash
python server.py
```

### 3. 💻 Start one or more clients (separate terminals)

```bash
python client.py
```

When prompted:
- enter a nickname
- enter password: `1234`

## ⌨️ Chat Commands

- **Group chat**: type and send any message
- **List users**: `lst_ppl`
- **Private message**: `private <nickname> <message>`

Example:

```text
private alice hey, are you free to chat?
```

## 📝 Notes

- Server is currently bound to `localhost`, so it is intended for local testing.
- Password is hardcoded for demo purposes; consider moving it to environment variables.
- The app uses ASCII encoding for messages.
