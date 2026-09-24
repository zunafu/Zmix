# 🎵 Zmix

A lightweight Discord music bot built with **Node.js**, **discord.js**, and **discord-player**.

Zmix allows users to play music in Discord voice channels, manage the playback queue, and control music through simple slash commands.

---

## ✨ Features

* 🎵 Play YouTube tracks
* 📋 Play YouTube playlists
* 🔎 Search and play music by keyword
* ⏸️ Pause and resume playback
* ⏭️ Skip the current song
* 🔢 Jump to a specific queue position
* 🔀 Shuffle the current queue
* 📜 View the music queue with pagination
* ℹ️ View current song information and playback progress
* 🚪 Leave the voice channel cleanly
* ⚡ Lightweight and easy to configure

---

## 📋 Commands

| Command                       | Description                                |
| ----------------------------- | ------------------------------------------ |
| `/play song <url>`            | Play a YouTube song                        |
| `/play playlist <url>`        | Play a YouTube playlist                    |
| `/play search <search terms>` | Search for and play music                  |
| `/pause`                      | Pause the current song                     |
| `/resume`                     | Resume playback                            |
| `/skip`                       | Skip the current song                      |
| `/skipto <position>`          | Jump to a specific queue position          |
| `/shuffle`                    | Shuffle the current queue                  |
| `/queue [page]`               | Display the current queue                  |
| `/info`                       | Display information about the current song |
| `/quit`                       | Leave the voice channel                    |

---

## 🛠️ Tech Stack

* [Node.js](https://nodejs.org/)
* [Discord.js v14](https://discord.js.org/)
* [Discord Player](https://discord-player.js.org/)
* [@discordjs/voice](https://www.npmjs.com/package/@discordjs/voice)
* [FFmpeg](https://ffmpeg.org/)
* [ffmpeg-static](https://www.npmjs.com/package/ffmpeg-static)
* [dotenv](https://www.npmjs.com/package/dotenv)

---

## 📦 Requirements

Before installing Zmix, make sure you have:

* Node.js installed
* A Discord account
* A Discord application and bot
* A Discord server where the bot can be used
* A Discord bot token
* Internet access

FFmpeg is included through the `ffmpeg-static` package.

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/zunafu/Zmix.git
cd Zmix
```

### 2. Install dependencies

```bash
npm install
```

### 3. Create the `.env` file

Create a `.env` file in the root directory:

```env
TOKEN=your_discord_bot_token_here
```

> ⚠️ **Never share or commit your Discord bot token.**

### 4. Configure `index.js`

Configure the following values in `index.js`:

```js
CLIENT_ID = "your_discord_application_id";
GUILD_ID = "your_discord_server_id";
```

| Configuration | Description                                             |
| ------------- | ------------------------------------------------------- |
| `CLIENT_ID`   | Your Discord application ID                             |
| `GUILD_ID`    | The Discord server ID where commands will be registered |

---

## ⚙️ Register Slash Commands

Before starting the bot, register the slash commands:

```bash
node index.js load
```

After successfully registering the commands, start the bot:

```bash
node index.js
```

---

## 📁 Project Structure

```text
Zmix/
├── index.js
├── package.json
├── Procfile
├── README.md
├── LICENSE
├── slash/
│   ├── info.js
│   ├── pause.js
│   ├── play.js
│   ├── queue.js
│   ├── quit.js
│   ├── resume.js
│   ├── shuffle.js
│   ├── skip.js
│   └── skipto.js
└── .env
```

### File Description

| File / Folder      | Description                                    |
| ------------------ | ---------------------------------------------- |
| `index.js`         | Bot setup, command loading, and event handling |
| `package.json`     | Project dependencies and configuration         |
| `Procfile`         | Deployment configuration                       |
| `slash/`           | Slash command files                            |
| `slash/play.js`    | Handles music playback                         |
| `slash/queue.js`   | Handles queue display                          |
| `slash/info.js`    | Displays current song information              |
| `slash/pause.js`   | Pauses playback                                |
| `slash/resume.js`  | Resumes playback                               |
| `slash/skip.js`    | Skips the current track                        |
| `slash/skipto.js`  | Jumps to a queue position                      |
| `slash/shuffle.js` | Shuffles the queue                             |
| `slash/quit.js`    | Disconnects the bot                            |
| `.env`             | Stores private environment variables           |

---

## 🌐 Deployment

Zmix includes a `Procfile` for platforms that support worker processes.

```text
worker: sh -c 'node index.js load && node index.js'
```

This command:

1. Registers the slash commands.
2. Starts the Discord bot.

> Deployment configuration may need to be adjusted depending on your hosting provider.

---

## 🔐 Environment Variables

The bot token should be stored in the `.env` file:

```env
TOKEN=your_discord_bot_token_here
```

Make sure `.env` is included in your `.gitignore`:

```gitignore
.env
node_modules/
```

**Never upload your bot token to GitHub.**

---

## 📝 Notes

* Zmix currently uses YouTube-based playback through `discord-player`.
* FFmpeg is provided through `ffmpeg-static`.
* Slash commands are currently registered for a single Discord guild.
* External music services may change their availability or behavior.
* For production deployments, use your hosting provider's secret-management system for sensitive credentials.

---

## 📄 License

Zmix is licensed under the **MIT License**.

See the [`LICENSE`](LICENSE) file for more information.

---

## 👤 Author

**zunafu**

* GitHub: [@zunafu](https://github.com/zunafu)
* Repository: [Zmix](https://github.com/zunafu/Zmix)

---

## ⭐ Support

If you find Zmix useful, consider giving the repository a ⭐ on GitHub.
