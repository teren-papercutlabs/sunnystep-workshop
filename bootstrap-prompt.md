# Bootstrap Prompt

Send this to the team. They paste it into Claude Code to set up their machine.

---

I'm setting up my machine for the Sunnystep AI Agent Workshop. Do the following:

1. **Install Ghostty** (terminal app) if not already installed. On macOS: `brew install --cask ghostty`. On Linux: follow https://ghostty.org/download.

2. **Configure Ghostty.** Read the config from https://raw.githubusercontent.com/teren-papercutlabs/sunnystep-workshop/main/ghostty/config and write it to the Ghostty config location:
   - macOS: `~/.config/ghostty/config`
   - Linux: `~/.config/ghostty/config`
   Create the directory if it doesn't exist.

3. **Install Espanso** (keyboard macro tool) if not already installed. On macOS: `brew install --cask espanso`. On Linux: follow https://espanso.org/install.

4. **Configure Espanso.** Read the match file from https://raw.githubusercontent.com/teren-papercutlabs/sunnystep-workshop/main/espanso/match.yml and write it to:
   - macOS: `~/Library/Application Support/espanso/match/sunnystep.yml`
   - Linux: `~/.config/espanso/match/sunnystep.yml`
   Create the directory if it doesn't exist.

5. **Restart Espanso** so it picks up the new macros: `espanso restart`

6. **Verify everything works:**
   - Open Ghostty — it should have a dark theme (Catppuccin Mocha) and JetBrains Mono font
   - In any text field, type `:para` — it should expand into a full prompt about paraphrasing
   - Confirm both are working and tell me the result

If anything fails, explain the error and fix it before moving on.
