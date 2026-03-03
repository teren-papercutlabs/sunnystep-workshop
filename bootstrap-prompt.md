# Bootstrap Prompt

Send this to the team. They paste it into Claude Code to set up their machine.

---

I'm setting up my machine for a workshop. I'm not technical — explain everything in simple language and walk me through each step. If anything needs a password or confirmation, tell me what to expect before I see it.

Do the following one step at a time. After each step, confirm it worked before moving to the next.

1. **Install workshop skills** — these are instructions that make Claude Code understand our brand and workflows. This is the most important step.
   - Clone the workshop repo: `git clone https://github.com/teren-papercutlabs/sunnystep-workshop.git ~/sunnystep-workshop`
   - Create the global skills directory if it doesn't exist: `mkdir -p ~/.claude/skills`
   - Copy each skill folder from the repo into global skills: `cp -r ~/sunnystep-workshop/.claude/skills/* ~/.claude/skills/`
   - Verify the skills are installed by listing them: `ls ~/.claude/skills/`
   - I should see folders like `agent-builder` and `frontend`. If not, something went wrong — fix it before moving on.

2. **Install Homebrew** — this is a tool that makes it easy to install other tools. macOS only — if I'm on Windows, skip this step.
   - I'll need to open my regular Terminal app (not Claude Code) and paste a command there. Tell me exactly what to paste and what to expect.
   - It will probably ask for my computer password — the one I use to log in. When I type it, nothing will appear on screen (no dots, no stars). That's normal. Just type it and press Enter.
   - This takes a few minutes. Tell me what "done" looks like.

3. **GitHub authentication** — GitHub is where our code will be saved. I need to log in so I can save my work there.
   - First check if `gh` (the GitHub tool) is installed. If not, install it for me.
   - Then run `gh auth login` and walk me through each choice it asks. Tell me what to pick at each prompt.

4. **Install Ghostty** — this is a nicer-looking terminal app. It's where we'll spend the day working.
   - macOS: install it using Homebrew.
   - Windows: tell me where to download it and walk me through the installer.
   - After installing, tell me how to open it.

5. **Configure Ghostty** — make it look good with a dark theme and clean font.
   - Read the config from https://raw.githubusercontent.com/teren-papercutlabs/sunnystep-workshop/main/ghostty/config
   - Write it to the right location (macOS: `~/.config/ghostty/config`, Windows: `%APPDATA%\ghostty\config`). Create the folder if it doesn't exist.
   - Tell me to close and reopen Ghostty to see the changes.

6. **Install Espanso** — this is a keyboard shortcut tool. When you type a short code like `:para`, it expands into a full sentence or prompt. Saves a lot of typing.
   - macOS: install it using Homebrew.
   - Windows: tell me where to download it and walk me through the installer.
   - It may ask for accessibility permissions on macOS. Walk me through granting that.

7. **Configure Espanso** — load the shortcuts we'll use today.
   - Read the shortcuts from https://raw.githubusercontent.com/teren-papercutlabs/sunnystep-workshop/main/espanso/match.yml
   - Write it to the right location (macOS: `~/Library/Application Support/espanso/match/sunnystep.yml`, Windows: `%APPDATA%\espanso\match\sunnystep.yml`). Create the folder if it doesn't exist.
   - Restart Espanso: `espanso restart`

8. **Verify everything works:**
   - Check skills are installed: `ls ~/.claude/skills/` — should show `agent-builder` and `frontend` folders.
   - Ask me to open Ghostty — it should have a dark theme and a clean monospace font.
   - Ask me to type `:para` in any text field — it should expand into a full prompt about paraphrasing.
   - If anything doesn't work, help me fix it before moving on.

9. **Ask me what else I need.** I may have other tools, accounts, or configurations to set up. Ask me one at a time.

If anything fails, explain what went wrong in simple language and fix it before moving on. Don't use jargon without explaining it first.
