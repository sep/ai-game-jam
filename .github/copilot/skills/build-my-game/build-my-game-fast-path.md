# Build My Game Fast Path

Use this as the operational fast path for /build-my-game runs.

- Start with vscode_askQuestions immediately.
- Ask the first question exactly as: What is your name?
- Use a single vscode_askQuestions call for the interview.
- Ask ALL of the following questions in a single vscode_askQuestions call, in this exact order and wording (verbatim):

  1. **Your Name** — "What's your name? (This will be used for your game's folder and credits)"

  2. **Game Genre** — "Pick a game type!" with options:
     - `Dodge It!` (description: "Dodge falling obstacles — survive as long as you can!")
     - `Collector` (description: "Collect items while avoiding hazards — grow your score!")
     - `Space Shooter` (description: "Fly a ship and blast enemies out of the sky!")
     - `Maze Runner` (description: "Navigate a 3D maze to find the exit before time runs out!")
     - `Endless Runner` (description: "Run forward, jump over gaps and slide under barriers!")
     - `Tower Defense` (description: "Place towers to stop waves of enemies marching across!")
     - `Brick Breaker` (description: "Paddle, ball, and colorful 3D blocks — smash them all!")
     - `Snake 3D` (description: "Grow your snake — don't hit yourself or the walls!")
     - `Asteroid Field` (description: "Pilot through spinning asteroids — don't crash!")
     - `Rhythm Runner` (description: "Notes fall toward you — press the right key at the right time!")
     - `Survival Arena` (description: "Waves of enemies close in — survive as long as you can!")
     - `Platformer` (description: "Jump between floating 3D platforms — don't fall!")

  3. **Game Setting** — "What world does your game live in?" with options:
     - `Outer Space` (description: "Stars, planets, and spaceships — pew pew!")
     - `Underwater` (description: "Deep sea with fish, submarines, and coral reefs")
     - `Medieval Fantasy` (description: "Knights, castles, dragons, and magic")
     - `City Streets` (description: "Cars, buildings, neon signs, and skyscrapers")
     - `Jungle` (description: "Vines, temples, wild animals, and ancient ruins")
     - `Arctic` (description: "Ice, snow, penguins, and polar bears")
     - `Haunted` (description: "Ghosts, pumpkins, bats, and spooky vibes")
     - `Candy Land` (description: "Lollipops, gummy bears, and chocolate rivers")
     - `Pirate Seas` (description: "Ships, cannons, treasure, and sea monsters")
     - `Cyberpunk City` (description: "Flying cars, holograms, neon rain, and robots")
     - `Custom` (description: "Describe your own world!")

  4. **Color Theme** — "Pick a vibe!" with options:
     - `Neon Cyber` (description: "Electric blues, hot pinks, glowing greens")
     - `Sunset` (description: "Warm oranges, reds, and purples")
     - `Ocean` (description: "Deep blues, teals, and seafoam")
     - `Forest` (description: "Greens, browns, and golden light")
     - `Monochrome` (description: "Clean black, white, and grays")
     - `Custom` (description: "Tell me your own colors!")

  5. **Special Feature** — "Want to add a twist? Pick one or describe your own!" with options:
     - `Speed Boost` (description: "Game gets faster over time!")
     - `Power-ups` (description: "Collect items for shields, magnets, or slow-mo")
     - `Boss Battle` (description: "A big enemy appears every 30 seconds")
     - `Gravity Flip` (description: "Press a key to flip gravity upside down")
     - `Multiplayer` (description: "Two players on same keyboard — WASD + Arrow keys")
     - `Day/Night Cycle` (description: "Scene shifts from bright to dark — enemies get harder at night!")
     - `Size Shifter` (description: "Press a key to shrink or grow — small fits through gaps, big smashes enemies!")
     - `Freeze Time` (description: "Charge a meter, then freeze all enemies for a few seconds!")
     - `Combo System` (description: "Chain actions without missing for a score multiplier!")
     - `Random Events` (description: "Every 15 seconds something wild happens — screen flips, speed changes, new enemies!")
     - `Magnet Mode` (description: "Collectibles pull toward you when you're nearby!")
     - `Portal Warp` (description: "Portals appear on the field — enter one, exit another!")
     - `Shield Bash` (description: "Press a key to activate a short shield that deflects enemies back!")
     - `Invisibility` (description: "Brief invisibility cloak on cooldown — enemies pass through you!")
     - `Trail of Fire` (description: "Leave a damaging trail behind you that hurts enemies!")
     - `Surprise me!` (description: "I'll pick something cool for you")

  6. **Game Title** — "Now that you know what your game is about, what do you want to call it?"

- Ask for the game title last, after gameplay and theme questions.
- Keep the interview tone friendly and supportive.
- Do not paraphrase or reword any required interview question text.
- If the askQuestions dialog is cancelled, do not edit files and retry using the same verbatim questions when the user resumes.
- Minimal required files after interview: games/_template/index.html and games/manifest.json.
- Avoid reading README.md, index.html, and styles.css unless the user asks to change the arcade site or docs.
- New participant games live at games/<filesystem-safe-name>/index.html.
- Games are single-file HTML with inline JS/CSS and Three.js r128 from CDN.
- Keep styling inside each participant game file; do not create per-game CSS files.
- Do not modify root index.html or styles.css unless the user asks for arcade-site changes.
