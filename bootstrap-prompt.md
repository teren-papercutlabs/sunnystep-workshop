# Bootstrap Prompt

Send this to the team. They paste it into Claude Code to set up their machine.

---

I'm setting up my machine for the Sunnystep AI Agent Workshop. Do the following:

1. **Install Homebrew** (macOS only) if not already installed. Run `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`. If already installed, skip.

2. **GitHub authentication.** Run `gh auth login` and walk me through the steps. I need to be able to push to repositories. If `gh` is not installed, install it first (`brew install gh` on macOS, or follow https://cli.github.com on Windows).

3. **Install Ghostty** (terminal app) if not already installed.
   - macOS: `brew install --cask ghostty`
   - Windows: follow https://ghostty.org/download

4. **Configure Ghostty.** Read the config from https://raw.githubusercontent.com/teren-papercutlabs/sunnystep-workshop/main/ghostty/config and write it to the Ghostty config location:
   - macOS: `~/.config/ghostty/config`
   - Windows: `%APPDATA%\ghostty\config`
   Create the directory if it doesn't exist.

5. **Install Espanso** (keyboard macro tool) if not already installed.
   - macOS: `brew install --cask espanso`
   - Windows: follow https://espanso.org/install

6. **Configure Espanso.** Read the match file from https://raw.githubusercontent.com/teren-papercutlabs/sunnystep-workshop/main/espanso/match.yml and write it to:
   - macOS: `~/Library/Application Support/espanso/match/sunnystep.yml`
   - Windows: `%APPDATA%\espanso\match\sunnystep.yml`
   Create the directory if it doesn't exist.

7. **Restart Espanso** so it picks up the new macros: `espanso restart`

8. **Verify everything works:**
   - Open Ghostty — it should have a dark theme (Catppuccin Mocha) and JetBrains Mono font
   - In any text field, type `:para` — it should expand into a full prompt about paraphrasing
   - Confirm both are working and tell me the result

9. **Ask me what else I need.** I may have other tools, accounts, or configurations to set up. Ask me one at a time.

If anything fails, explain the error and fix it before moving on.
