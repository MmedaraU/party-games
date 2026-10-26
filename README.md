# 🎈 The Hangout

<p align="center">
  <strong>A single-file, offline-capable party game for friends.</strong><br>
  Banter, dares, trivia, and confessions. Play on one device or sync a whole room.
</p>

Built as one HTML file with zero build steps, zero backend, and zero accounts. Drop it on any static host, share the link, and play.

> Looking for the couples version? That lives [here](https://github.com/MmedaraU/us-two) with its own README.

---

## Features

- **1,300+ prompts** across seven distinct decks — from lighthearted banter to deep conversations and spicy confessions.
- **Merged "Hot Takes & Dilemmas"** — Combines controversial opinions with fast-paced "Would You Rather" scenarios into one massive, argument-starting deck.
- **Merged "NHIE & Confessions"** — A combined 18+ scoring deck. Everyone votes "I HAVE" or "I HAVEN'T" on their own device, and the host reveals a live scorecard showing exactly who did what and how many points they lost.
- **Real-time Party Mode** — One host, unlimited guests. Everyone sees the same card. Guests dedup on rejoin via a persistent client ID. The host is included in the final podium.
- **Seating-Agnostic Realtalk** — Prompts are framed as "Pick someone in the room" or "The person who spoke last," so the game works flawlessly in a circle, on a couch, or over a video call.
- **Charades & Trivia** — A massive acting deck (including Bible mimes) and a mixed Bible Trivia/Riddle deck with hints and answers.
- **Dark mode** — Light, Dark, and System themes, saved per device, with no flash of light content on load.
- **Fully responsive** — Works beautifully on phones, tablets, and laptops.

---

## Quick Start

### On one device
1. Download `index.html` (or copy the code into a file with that name).
2. Double-click it to open in any modern browser.
3. Pick a deck, tap **Next Card**, and read the prompt aloud.

### Long-distance or multiple devices
1. Open the file on one device and tap **🎉 Party → Host a Party**.
2. Share the 4-character code, link, or QR code with your friends.
3. They open the link or join by typing the code. Both screens will stay in perfect sync.

*Party Mode requires internet access for the initial WebRTC peer connection. Solo mode works fully offline.*

---

## How to Play

- **Next Card:** Tap the button, swipe left, or press `Space / → / Enter`.
- **Action Cards:** Tap **😎 EASY** or **❌ NO CHANCE** (press `1` or `2`). Choosing either fires confetti and moves to the next card automatically.
- **Scoring Cards (NHIE & Confessions):** Everyone taps **✋ I HAVE** or **🙅 I HAVEN'T** on their own device. When the host taps Reveal, a live scorecard appears showing exactly what everyone voted and their new scores. 
- **Trivia Cards:** Tap **💡 Hint** for a nudge, or **👁️ Reveal Answer** to see the solution. If you're a guest, type your guess into the box to see if you match. 
- **The Guide:** A 9-step interactive guide appears on first open. You can reopen it anytime with the **❓** button in the header.

---

## The Decks

| Deck                   | Emoji | Count   | Style                                               | Adult   |
| :--------------------- | :---- | :------ | :-------------------------------------------------- | :------ |
| Banter                 | 🍿     | **166** | Nigerian & friendship banter                        | No      |
| Heart to Heart         | 💗     | **100** | Deep questions, perception, and reflection          | No      |
| Easy or No Chance      | 😎     | **86**  | Dares and physical challenges                       | No      |
| Charades               | 🎭     | **200** | Acting out general & Bible scenes                   | No      |
| Bible Trivia & Riddles | ✝️     | **239** | Trivia questions and riddles                        | No      |
| Hot Takes & Dilemmas   | 🔥     | **368** | Controversial opinions and "Would You Rather"       | No      |
| NHIE & Confessions     | 🫣     | **167** | "Never Have I Ever" and spicy confessions           | **18+** |
| **Classic Mix**        | 🎲     | **959** | Banter, Dares, Trivia, and Hot Takes shuffled       | No      |
| **Scoring Deck**       | 🏆     | **167** | Played with the live "I HAVE / I HAVEN'T" voting UI | **18+** |

---

## Safety & Privacy

- **Consent is continuous.** Ticking the 18+ gate is the start of consent, not the end. Anyone can stop, pause, or skip at any time.
- **Skip is always free.** Skipping has no counter, no record, and no penalty.
- **Privacy:** Everything runs in the browser. Party Mode is peer-to-peer; the only data leaving your device is the current card, the draw counters, and the votes for scoring decks.

---

## Technical Stack & Customization

- **Stack:** HTML, CSS, Vanilla JavaScript. No frameworks, no build steps.
- **Sync:** WebRTC via [PeerJS](https://peerjs.com/). 
- **Audio/Visuals:** Canvas 2D (confetti) and Web Audio API (synthesized sounds).
- **Storage:** LocalStorage is used to remember your theme and sound preference.

### Customizing the Game
All content is managed in the `<script>` tag in `index.html`:
- `RAW`: The actual prompt arrays. Add strings for plain cards, or `{ text: "...", answer: "...", hint: "..." }` for trivia cards.
- `RAW_SOURCES`: Maps your deck keys to one or more prompt arrays. This is how you merge decks (e.g., `nhie: ["nhie", "confessions"]`).
- `DECKS`: Defines the deck labels, emojis, colors, and whether they are `mature` or `scoring`.
- `FILTERS`: Defines what appears in the game selection menu.

---

## Deployment

Everything lives in a single HTML file. Host it anywhere static. **HTTPS is required for Party Mode** (WebRTC).

- **GitHub Pages:** Commit the file, go to Settings → Pages, and select your branch.
- **Netlify:** Drag the folder onto [app.netlify.com/drop](https://app.netlify.com/drop).
- **Vercel:** Run `vercel --prod` in the directory.

---

## License

Free to use, modify, and share for personal use. All prompt content is original and written for this project. **Play responsibly.**