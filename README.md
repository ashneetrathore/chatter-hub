# :speech_balloon: CHATTER HUB

## :open_book: OVERVIEW
Date: March 2022\
Developer(s): Ashneet Rathore, Sachita Jnanesh Rayapati, Roselene Ujagar

Chatter Hub is a distributed social messenging application for sending and receiving messages through a DSU server. Users can create new profiles or load existing ones, add contacts, and chat with others in real time.

## :film_strip: DEMO
![Demo](demo.gif)

## :classical_building: ARCHITECTURE
The application follows a **client-server architecture** implemented in **Python**. The frontend, built with **Tkinter**, provides an interactive GUI for composing, sending, and receiving messages. User profiles are stored locally as `.dsu` files and can be created or loaded at startup. The backend uses **socket programming** to communicate with the DSU server over TCP, following a **JSON-based messaging protocol**.

## :open_file_folder: PROJECT FILE STRUCTURE
```bash
chatter-hub/
│── src/
│   │── main.py              # Tkinter GUI and main app logic
│   │── profile.py           # Profile storage and loading logic
│   │── ds_messenger.py      # Messaging logic
│   └── ds_protocol.py       # Messaging protocol with JSON encoding and decoding
│── README.md                # Project documentation
│── .gitignore               # Ignored files
└── demo.gif                 # Demo GIF
```

## :hammer: CONFIGURATION
**1. Clone the repository**
```bash
git clone https://github.com/ashneetrathore/chatter-hub.git
```

**2. Assign a valid DSU server address to `DSU_SERVER_ADD` in ```main.py```**
```python
# Example assignment
DSU_SERVER_ADD = "127.0.0.1"
```

**3. Assign a valid DSU server port to `DSU_SERVER_PORT` in ```ds_messenger.py```**
```python
# Example assignment
DSU_SERVER_PORT = 5000
```

## :rocket: EXECUTION
```bash
cd chatter-hub/src
python main.py
```

## :wrench: TRY IT OUT
To test without multiple devices, run two instances of the app on the same machine - one for each user.

**Set up two profiles**
1. Click `File` in the menu bar and select `New`.
2. Enter a username (e.g. *user1*) and password when prompted.
3. Choose a location to save the `.dsu` file.
4. Open a second terminal, launch the app again, and repeat steps 1-3 with a different username (e.g. *user2*).

**Add each other as contacts**

5. In user1's app, click `Settings` in the menu bar, select `Add Contact`, and enter *user2*.
6. In user2's app, repeat with *user1*.

**Send messages**

7. In both apps, select the other user from the contact list.
8. Type a message in user1's app and click `Send`. It should appear in user2's app after a short delay.
9. Repeat from user2's app to send a message back.