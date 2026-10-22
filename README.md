# Guess The User — Out-of-Context Discord Trivia & Deduction Game

<div align="center">
  <h3>The Out-of-Context Discord Trivia & Deduction Party Game</h3>
  <p>Playable directly in your browser or inside Discord Voice Channels as an Embedded App Activity</p>

  [![Platform: Web | Discord](https://img.shields.io/badge/Platform-Web%20%7C%20Discord%20Activity-blue?style=flat-square)](#1-screenshots-showcase)
  [![Frontend: React 19](https://img.shields.io/badge/Frontend-React%2019%20%7C%20TypeScript%20%7C%20Vite-61DAFB?style=flat-square&logo=react&logoColor=black)](#technical-stack--architecture)
  [![Styling: Tailwind CSS](https://img.shields.io/badge/Styling-Tailwind%20CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)](#technical-stack--architecture)
  [![Multiplayer: PeerJS](https://img.shields.io/badge/Multiplayer-PeerJS%20%28WebRTC%29-EB459E?style=flat-square)](#technical-stack--architecture)
  [![Hosting: Cloudflare Pages](https://img.shields.io/badge/Hosting-Cloudflare%20Pages%20%7C%20Railway-F38020?style=flat-square&logo=cloudflare&logoColor=white)](#technical-stack--architecture)
  [![Privacy: Zero-Knowledge](https://img.shields.io/badge/Privacy-100%25%20Client--Side%20Zero--Knowledge-brightgreen?style=flat-square)](#3-privacy--architecture-highlights)
  [![Status: Showcase Only](https://img.shields.io/badge/Repository-Showcase%20%28No%20Code%29-lightgrey.svg)](#source-code-notice)

  <br />

  <a href="https://guesstheuser.com"><img src="https://img.shields.io/badge/Live%20App-guesstheuser.com-5865F2?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Live App" /></a>
  <a href="https://discord.com/oauth2/authorize?client_id=1545362524751532082&permissions=68608&scope=bot%20applications.commands"><img src="https://img.shields.io/badge/Discord%20Activity-Launch%20in%20Voice-57F287?style=for-the-badge&logo=discord&logoColor=white" alt="Discord Activity" /></a>
  <a href="https://buymeacoffee.com/kevnev"><img src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-Support-FEE75C?style=for-the-badge&logo=buymeacoffee&logoColor=black" alt="Support" /></a>
</div>

---

> **Guess The User** turns a server's hilarious, unhinged, and out-of-context quotes into a high-stakes deduction party game. Given an isolated message taken from your community's history, players have 5 progressive clue frames to deduce which server member said it. Context clues gradually unmask neighboring conversation logs, timestamps, channel hints, and Yellow Chatter indicators.

---

## 1. Screenshots Showcase

### Web Application

<div align="center">
  <table>
    <tr>
      <td align="center" width="50%">
        <img src="screenshots/website/landing.png" alt="Web Landing View" width="400" /><br />
        <b>Interactive Landing Screen</b><br />
        <i>Zero-friction startup with pre-bundled demo servers and custom challenge imports</i>
      </td>
      <td align="center" width="50%">
        <img src="screenshots/website/gameplay.png" alt="Web Gameplay View" width="400" /><br />
        <b>5-Frame Deduction Gameplay</b><br />
        <i>Progressive quote reveal, strike indicators, and avatar search filter</i>
      </td>
    </tr>
  </table>
</div>

---

### Discord Voice Channel Activity (Embedded App SDK)

Launch the game natively inside Discord voice chat with full support for Co-Op and Competitive party modes:

<div align="center">
  <table>
    <tr>
      <td align="center" width="50%">
        <img src="screenshots/discord-activity/coop_mode.png" alt="Discord Co-Op Mode" width="400" /><br />
        <b>Co-Op Party Deduction</b><br />
        <i>Collaborate in voice chat to solve server quote puzzles together</i>
      </td>
      <td align="center" width="50%">
        <img src="screenshots/discord-activity/compete_mode.png" alt="Discord Compete Mode" width="400" /><br />
        <b>Real-Time Compete Tournament</b><br />
        <i>Synchronized countdown timers, dynamic scores, and early-skip guards</i>
      </td>
    </tr>
  </table>
</div>

---

## 2. Core Gameplay Mechanics

### Progressive 5-Frame Scoring Matrix
Players earn points based on how few clues they need to guess the author:

| Frame | Clue Revealed | Max Score | Deduction Strategy |
| :---: | :--- | :---: | :--- |
| **Frame 1** | Target Quote (Clean text only) | **50 pts** | Identify distinct vocabulary, catchphrases, or inside jokes. |
| **Frame 2** | Preceding message unmasked | **40 pts** | Notice who replied to whom or what prompted the comment. |
| **Frame 3** | Subsequent reply unmasked | **30 pts** | Track reactions, nicknames, or conversational tone. |
| **Frame 4** | Surrounding thread context | **20 pts** | Reveal topic shifts, banter, and conversation flow. |
| **Frame 5** | Full thread + Channel name hint | **10 pts** | Channel topic narrows down the candidate pool. |

### Yellow Chatter Indicators
* **Blue Messages**: Messages authored by the mystery target user.
* **Yellow Messages**: Messages mentioning or reacting to the mystery user.
* **Grey Messages**: Background conversation noise from other server members.

### Game Modes
* **Solo Practice / Daily Seed**: Endless random challenges with streaks and daily challenges.
* **Co-Op Party Mode**: Play with friends in voice chat where everyone shares clues and guesses together.
* **Compete Tournament**: Race against the clock where each player guesses individually on their own board while the live scoreboard tracks attempts in real time.

---

## 3. Privacy & Architecture Highlights

Guess The User was engineered from day one with **Zero-Knowledge Privacy**:

* **100% Client-Side Processing**: No Discord messages, logs, or user IDs are stored on any backend database.
* **Local IndexedDB Cache**: Imported server archives remain isolated inside the player's local browser storage.
* **Transient Real-Time Multiplayer**: Multiplayer rooms synchronize state peer-to-peer via WebRTC (`PeerJS`), meaning game moves are directly exchanged between clients without central persistence.
* **Platform Compliance**: Instant deletion compliance and zero third-party commercial tracking ads.

---

## Technical Stack & Architecture

* **Frontend**: **React 19**, **TypeScript**, **Vite**, **Tailwind CSS**, Lucide Icons, and Canvas Confetti.
* **Networking & Real-Time Sync**: **PeerJS (WebRTC)** for serverless peer-to-peer room state replication; **Discord Embedded App SDK** for native voice channel integration.
* **Backend & Companion Bot**: **Node.js**, **Express**, and **Discord.js v14** hosted on **Railway** for token auth and room signaling.
* **Hosting & CDN**: **Cloudflare Pages** (Frontend CDN) and **Railway** (Bot & WebSocket Signaling).
* **Audio Synthesis**: **Web Audio API** procedural synthesis for custom Discord-themed chimes and countdown soundscapes.

---

## Source Code Notice

> **Notice**: This repository is a **public showcase and architectural summary**. The core source code is maintained in a private repository while multiplayer scaling audits are completed.  
> Demos and technical walkthroughs are available upon request for interview purposes.

---

## Project Links & Resources

* **Live Website**: [guesstheuser.com](https://guesstheuser.com)
* **Add Discord Bot**: [Bot Authorization & Activity Invite](https://discord.com/oauth2/authorize?client_id=1545362524751532082&permissions=68608&scope=bot%20applications.commands)
* **How to Play Guide**: [guesstheuser.com/how-to-play.html](https://guesstheuser.com/how-to-play.html)
* **Support the Creator**: [buymeacoffee.com/kevnev](https://buymeacoffee.com/kevnev)

---

## License

This showcase repository is released under the [MIT License](LICENSE).  
Built for Discord communities by [Kevin](https://github.com/kevnevv).
