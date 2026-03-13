# 🎮 ONE SHOT GAMES — Build & Host Your Own with Claude + GitHub Pages
## Full YouTube Tutorial Script

---

## SECTION 1: HOOK (0:00 – 1:30)

**[On camera, energetic opener]**

"What if you could build a fully playable browser game, host it for free, and share it with anyone in the world — all in about 20 minutes, with zero server setup, zero backend, and zero dollars? That's exactly what we're doing today.

I'm going to show you how to build what I call **One Shot Games** — single-file HTML games that run entirely in the browser, no install required, no saves, no continues. You just open the page and play. Think arcade-era energy in a modern wrapper.

By the end of this video you'll have your own game arcade hosted live on GitHub Pages. We're going to use Claude as our co-developer, and I'll show you the exact prompts to use.

Let me show you the finished product first so you know where we're headed."

**[Screen share — show the live site]**

"This is The Daily Babel — my own one-shot arcade. CRT scanlines, retro aesthetic, five games live right now. Every single one of these is a single HTML file. No frameworks, no npm install, no build step. Just one file, open in any browser, game works.

Castle Wolfenstein. Lucky Sevens Slots. Lunar Lander. Titanic. Vortex Command. All of them — one file each.

Here's the best part: this whole thing lives on GitHub Pages, which means it's **completely free** to host forever. Let's build it."

---

## SECTION 2: WHAT ARE ONE-SHOT GAMES? (1:30 – 4:00)

**[Talking head or screen share with diagram]**

"Quick concept check — what makes a One Shot game different from any other browser game?

Three rules:

**Rule one: One file.** Everything — the HTML structure, the CSS styling, the JavaScript game logic, the sounds, the fonts — is packed into a single `.html` file. You could email this file to someone and they could open it offline and play it. That's the test.

**Rule two: No saves.** When you close the tab, the game is gone. No localStorage persistence across sessions, no high score leaderboards that survive a refresh. This is actually a design *feature* — it creates a tension that every session is its own story. 

**Rule three: Self-contained.** External CDN fonts are okay. But no API keys, no databases, no server calls that require auth. The game should run fine if you download the HTML and open it in a plane with no WiFi.

This constraint is actually what makes them so fun to build with AI. Claude can hold an entire game in its context window. You give it a brief, it gives you a complete file, and you're done. No architecture decisions, no dependency hell, no deployment pipeline.

Now — why GitHub Pages? Because it's free, it's fast, it's reliable, and it's where your code already lives. GitHub serves static HTML files perfectly. One repo, one settings toggle, and your game is live on a public URL."

---

## SECTION 3: PREREQUISITES & SETUP (4:00 – 8:00)

**[Screen share]**

"Here's everything you need before we start, and I promise the list is short.

**What you need:**
- A GitHub account — free at github.com
- Git installed on your machine — I'll link the install page in the description
- A text editor — VS Code is what I'll use but Notepad works in a pinch
- A Claude account — free tier at claude.ai works, Pro makes your games fancier

That's it. No Node.js required for the games themselves. No package manager. No build tools.

**[Show GitHub account creation if needed, or skip if audience is technical]**

Let's set up the repository. Head to GitHub, click the plus icon, New Repository.

**Repository settings that matter:**
- Name it something cool — mine is `thedailybabel.com` but `my-arcade` works fine
- Set it to **Public** — GitHub Pages requires public repos on the free tier
- Check **Add a README file** — this creates the main branch automatically
- Leave everything else default

**[Show creating the repo]**

Click Create Repository. Now we need to enable GitHub Pages.

Go to **Settings** → **Pages** → under Source, select **Deploy from a branch** → choose `main` branch, `/ (root)` folder → hit Save.

**[Show the settings page]**

GitHub will give you a URL — something like `yourusername.github.io/my-arcade`. This is where your arcade will live. It might take a minute or two to go live the first time, but once it's set up, every time you push a file to main, it deploys automatically. Magic.

Now let's clone the repo locally so we can add games."

**[Show terminal]**

```bash
git clone https://github.com/yourusername/my-arcade.git
cd my-arcade
```

"You're in. Let's make a game."

---

## SECTION 4: BUILD YOUR FIRST GAME WITH CLAUDE (8:00 – 22:00)

**[Screen share — Claude interface]**

### 4a: The Prompt Philosophy (8:00 – 11:00)

"Before I paste a prompt, let me explain the prompting strategy. When you're asking Claude to build a one-shot game, you need to be specific about three things:

**One — the file constraint.** Explicitly say 'single HTML file, all CSS and JavaScript inline.' Claude is trained to suggest frameworks and build tools, and you want to override that instinct.

**Two — the one-shot philosophy.** Tell Claude there are no saves, no continues. One session is one game. This changes how Claude designs the game loop.

**Three — the visual style.** Do you want retro terminal aesthetic? Pixel art? Minimal clean? Give Claude a visual brief and it'll carry it through the whole file consistently.

Here's my base template prompt — I'm going to put this in the description and the cheat sheet:"

**[Show the prompt on screen]**

```
Build me a one-shot browser game called [GAME NAME].

Rules:
- Single HTML file. All CSS and JavaScript must be inline. No external 
  dependencies except Google Fonts if needed.
- No save states, no localStorage persistence between sessions.
- The game ends when the player wins or loses — no continues.

Game concept: [2-3 sentences describing what the player does, 
the win condition, and the lose condition]

Visual style: [e.g., "CRT terminal aesthetic — dark background, 
amber/green neon colors, scanline overlay, monospace fonts"]

When complete, output the full HTML file content only.
```

"Let me show you this in action."

### 4b: Live Demo — Building Lunar Lander (11:00 – 18:00)

**[Screen share — Claude conversation]**

"Let's build something with real physics — a Lunar Lander clone. Here's my prompt:"

**[Paste and send the prompt with specifics filled in]**

"Game concept: The player pilots a lunar module descending toward the moon's surface. Use arrow keys to fire thrusters. Fuel is limited. The player must reduce vertical and horizontal velocity enough to land safely on the marked pad. Too fast or off-target is a crash. Too much fuel use and they fall uncontrolled.

Visual style: Dark space background with stars, pixel-style terrain, glowing thruster effects, fuel gauge and velocity readout in terminal-style font."

**[Wait for Claude to respond — narrate what's happening]**

"Watch what Claude does here — it's thinking through the physics engine, the game loop, the input handling, the collision detection, all at once. And it's going to give us one complete file.

This is the magic of the constraint. When you tell Claude 'one file,' it stops trying to architect a system and just... builds the game. It's a fundamentally different mode."

**[Show the output arriving]**

"Okay, we've got our file. Let me save this."

**[Show saving to the repo folder]**

```bash
# In your my-arcade directory
# Save the file Claude gave you as:
lunar-lander.html
```

"Open it in your browser:"

```bash
open lunar-lander.html  # Mac
# or just double-click the file
```

**[Show the game running]**

"There it is. A physics-based lunar lander, running entirely in a browser, zero dependencies, one file. Let's test it — I'm going to crash spectacularly on purpose just to show the game-over screen works."

**[Play the game briefly, then crash]**

"Perfect. Now let's talk about one common issue you'll hit — and how to fix it."

### 4c: Iteration & Debugging (18:00 – 22:00)

**[Screen share]**

"Claude gets it right about 80% of the time on the first try. For the other 20%, you iterate. Here's my debugging workflow.

**Problem type 1: Broken gameplay.** Something doesn't work — collision detection is off, the game ends too early, controls feel wrong. Go back to Claude and be specific:

'The thruster controls feel too sensitive. The ship accelerates too fast. Reduce the thrust force by half.'

Or paste the specific broken section of JavaScript and ask:
'This collision detection function is not triggering when the ship hits the terrain. Debug it and fix it.'

**Problem type 2: Cosmetic issues.** The game works but looks rough. Easy fix:
'The fuel gauge looks like an afterthought. Redesign it as a proper terminal-style readout with amber color and a label.'

**Problem type 3: The whole file is a mess.** Sometimes Claude gets tangled in a long session. Nuclear option:
'Start over. Here are my requirements. Output a clean, final version of the complete HTML file.'

The key thing: Claude maintains context within a conversation. Keep your game-building in one Claude conversation. If you start a new chat, start fresh — don't expect Claude to remember the old file.

When you're happy with the game, save the final version to your repo folder."

---

## SECTION 5: BUILDING THE ARCADE INDEX PAGE (22:00 – 32:00)

**[Screen share]**

"One game is great. An arcade with five games is a destination. Let's build the index page.

Your index page has two jobs: look incredible, and link to your games. That's it. No backend, no dynamic content — pure HTML and CSS.

Here's how I prompt for it:"

**[Show in Claude]**

```
Build me an arcade lobby page in a single HTML file.

It should display a grid of game cards. Each card links to a game file:
- lunar-lander.html — Lunar Lander 🚀
- [your other games here]

Visual style: [describe your aesthetic]

The page should have:
- A title at the top
- A grid of clickable game cards, each with an emoji, game title, 
  and one-sentence description
- Hover effects on the cards
- A footer

Output the full HTML only. All links are relative (just the filename, 
no full URL path).
```

**[Show the output]**

"Save this as `index.html` in your repo root. This is critical — GitHub Pages serves `index.html` as the homepage automatically.

**[Show saving the file]**

Let me show you something important about the links. In your index page, links to games should look like this:"

**[Show code snippet]**

```html
<a href="lunar-lander.html">Play</a>
```

"Not like this:"

```html
<a href="/my-arcade/lunar-lander.html">Play</a>  ← WRONG
<a href="https://github.com/...">Play</a>          ← WRONG
```

"Relative links. Filename only. This is what makes the whole thing work both locally and on GitHub Pages."

**[Show folder structure]**

"Here's what your repo folder should look like right now:"

```
my-arcade/
├── index.html          ← Your lobby
├── lunar-lander.html   ← Game 1
├── README.md           ← Auto-created by GitHub
```

"Clean. Simple. Every game is one file at the root level."

---

## SECTION 6: DEPLOY TO GITHUB PAGES (32:00 – 37:00)

**[Screen share — terminal]**

"Time to go live. Three commands:"

```bash
git add .
git commit -m "Add lunar lander and lobby"
git push origin main
```

**[Run the commands, show output]**

"That's it. GitHub receives the push, GitHub Pages builds it — which takes about 30–60 seconds — and your arcade is live.

Let's check:"

**[Open browser, navigate to the GitHub Pages URL]**

"There it is. Live on the internet. Anyone in the world can play this right now. Let me open the game from the lobby."

**[Click through, show the game loading]**

"Works perfectly. And notice the URL — it's your GitHub Pages URL, clean, no `index.html` needed, no port numbers, no localhost. This is a real live website.

Let me show you the deploy flow you'll use going forward. Every time you:
1. Build a new game with Claude
2. Save the HTML file to your repo folder  
3. Add a card for it in index.html
4. Run `git add . && git commit -m 'Add [game name]' && git push`

That's it. New game is live in under a minute."

---

## SECTION 7: TIPS, TRICKS & DESIGN PRINCIPLES (37:00 – 45:00)

**[Talking head or screen with examples]**

### Visual Consistency

"Your arcade will look like a cohesive product if all your games share a visual language. The easiest way to do this: **define a style brief once and include it in every prompt**.

My brief: dark background (#080c10), CRT scanline overlay, neon accent colors, monospace fonts from Google Fonts, clip-path cut corners on cards. I paste this or a summary of it into every game prompt. Claude picks it up and runs with it.

### The One-Shot Design Challenge

"Here's a creative direction I love pushing: make the one-shot constraint *part of the game*. Don't just remove saves — design for it.

Examples:
- A game where your choices permanently affect what's available (you burned a bridge, it stays burned)
- A game where the clock counts up, not down — your 'score' is how long you survived
- A game where knowing you can't retry makes every decision feel heavier

Tell Claude: 'Design this as a true one-shot experience. The single-session constraint should feel intentional, not like a missing feature.'

### Game Ideas That Work Great as One-Shots

"Some genres translate perfectly to the single-file, no-save format:"

- **Physics-based games** — Lunar Lander, pool, catapult, ballistics
- **Card and dice games** — Blackjack, poker variants, dice games
- **Arcade classics** — Space Invaders-style, Breakout, simple platformers
- **Text adventure / choice games** — branching narrative, finite paths
- **Puzzle games** — Sudoku, sliding puzzles, logic grids
- **Strategy lite** — Simple resource management, tower defense

"What doesn't work well: games that need persistent accounts, multiplayer, or 100+ MB of assets. Stay in the 'one browser tab' mental model and you'll stay in scope.

### Debugging Tips

"A few things that trip people up:

**Fonts not loading?** Claude sometimes uses fonts that need a Google Fonts import link. If the font looks wrong, check the `<head>` for a `<link rel='stylesheet' href='https://fonts.googleapis.com/...'>` tag. If it's missing, ask Claude to add it.

**Game runs locally but breaks on GitHub Pages?** Almost always a path issue. Check that all your file references are relative — no `/` at the start, no absolute URLs.

**Game is too easy or too hard?** The fastest fix is a simple Claude prompt: 'The game is too easy. Increase difficulty by 30% — faster enemies, less starting fuel, tighter timing window.' Claude can tune parameters precisely.

**Mobile doesn't work?** Add 'Make sure this works on mobile with touch controls' to your game prompt. Claude will add touch event handlers alongside keyboard controls.

### Customizing for Your Brand

"Your lobby page is the face of your arcade. Some things worth customizing:

- **Name it something.** 'My Arcade' is fine for day one; come up with a real name. It makes the project feel like a project.
- **Write real descriptions.** Don't use the default text Claude generates — write your own voice into the card descriptions.
- **Pick your colors.** Amber/neon is my choice. Yours could be all cyan, or monochrome, or brutalist primary colors. The constraint is just: be consistent.
- **Link to your GitHub in the footer.** It's a portfolio piece. Own it."

---

## SECTION 8: ADVANCED: ADDING A RULES/ABOUT PAGE (45:00 – 50:00)

**[Screen share]**

"One optional but powerful addition: a rules or about page. This is just another HTML file — `rules.html` or `oneshot.html` — linked from your lobby.

For my site I have a page that explains the one-shot philosophy, gives hints for the games, and links back. Prompt for it:"

```
Create a single-page HTML document that explains the One Shot Games 
concept and philosophy. 

Include:
- A hero section explaining what 'one shot' means
- A section listing the rules (no saves, no continues, one session)
- Game tips or hints section
- A link back to the lobby (index.html)

Visual style: [match your arcade style]
```

"Link to it from your lobby with a simple relative link. Another file, another git push, another page live."

---

## SECTION 9: RECAP & NEXT STEPS (50:00 – 53:00)

**[On camera]**

"Let's recap what we built today.

You have a GitHub repo with GitHub Pages enabled. You have a lobby page — `index.html` — that links to your games. You have at least one complete, playable, self-contained browser game. And you know the exact workflow to add more games in 20 minutes flat.

The workflow is:
1. Write a game brief
2. Prompt Claude with the one-shot template
3. Save the HTML file to your repo
4. Add a card to index.html
5. `git add . && git commit && git push`
6. Game is live

**What's next?** Build more games. Add a new one every week. Get weird with the one-shot constraint — design mechanics that lean into no-saves. Share your arcade URL in the description of any game you make as a social media post and see what happens.

I have links in the description to the full prompt template, the cheat sheet PDF, and my own arcade so you can play the games we talked about.

If you build something, I genuinely want to see it. Drop the link in the comments.

Subscribe if you want more builds like this — I'm going to do a follow-up on making one-shot games with procedural generation so every play-through is different even without saves.

See you in the next one."

---

## [END CARD — 53:00 – 55:00]

**[Show outro with links:]**
- Download the Cheat Sheet (link)
- View The Daily Babel arcade (link)
- Prompt template (link or show on screen)
- Subscribe CTA

---

## APPENDIX: FULL PROMPT TEMPLATES

### Base Game Prompt
```
Build me a one-shot browser game called [GAME NAME].

Rules:
- Single HTML file. All CSS and JavaScript must be inline. 
  No external dependencies except Google Fonts if needed.
- No save states, no localStorage persistence between sessions.
- The game ends when the player wins or loses — no continues.

Game concept: [2-3 sentences: what the player does, win condition, lose condition]

Visual style: [describe your aesthetic — colors, fonts, vibe]

When complete, output the full HTML file content only.
```

### Lobby / Index Page Prompt
```
Build me an arcade lobby page in a single HTML file.

Games to include:
- [filename.html] — [Game Title] [emoji]: [one sentence description]

Visual style: [your aesthetic]

Requirements:
- Page title and subtitle at the top
- Game cards in a CSS grid, each clickable, linking to the game file
- Hover effects on cards
- Footer with your name/link
- All game links are RELATIVE (filename only, no path prefix)

Output the full HTML only.
```

### Iteration / Fix Prompt
```
Here is the current version of my game HTML: [paste file]

Issue: [describe the specific problem]

Fix only this issue. Output the complete updated HTML file.
```
