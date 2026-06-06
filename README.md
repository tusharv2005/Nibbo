<p align="center">
  <img src="assets/tray-icon.png" width="128" alt="Nibbo">
</p>
<h1 align="center">Nibbo</h1>

<p align="center">
  <a href="https://github.com/tusharv2005/Nibbo/releases"><img src="https://img.shields.io/github/v/release/tusharv2005/Nibbo" alt="Version"></a>
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey" alt="Platform">
  <a href="https://github.com/tusharv2005/Nibbo/stargazers"><img src="https://img.shields.io/github/stars/tusharv2005/Nibbo?style=flat&logo=github&color=yellow" alt="Stars"></a>
  <a href="https://github.com/hesreallyhim/awesome-claude-code"><img src="https://awesome.re/mentioned-badge-flat.svg" alt="Mentioned in Awesome Claude Code"></a>
</p>

<p align="center">
  <img src="assets/hero.gif" alt="Nibbo — a pixel desktop pet that reacts to your AI coding agent in real time. Animated demo: the pet cycles through sleeping, thinking while the model reads the codebase, typing as edit/bash tools run, grooving for one subagent, juggling when multiple subagents run, raising a permission bubble, and celebrating when 14 files / 312 tests are complete. Works with Claude Code, Codex, Cursor, Copilot, Gemini, Antigravity, Qwen, Pi, OpenClaw and more.">
</p>

Nibbo is a premium, real-time desktop companion that visualizes what your AI coding agents are doing. Start a long task, walk away, and look back at your screen to see if Nibbo is thinking, working, or celebrating a completed task.

Nibbo features rich, cozy visuals and real-time state animations—thinking when your agent is prompted, typing when it executes tools, grooving or juggling for subagents, prompting you with custom desktop permission bubbles, and falling asleep when the desk is quiet. 

It comes with four built-in themes: **Clawd** (pixel crab), **Calico** (cozy tortoiseshell cat), **Cloudling** (fluffy cloud), and **Dewdrop** (green slime sprout), with full support for custom themes and imported Codex Pet animation packs.

> Works with **Claude Code**, **Codex CLI**, **Copilot CLI**, **Gemini CLI**, **Antigravity CLI (agy)**, **Cursor Agent**, **CodeBuddy**, **Kiro CLI**, **Kimi Code CLI (Kimi-CLI)**, **Qwen Code**, **opencode**, **Pi**, **OpenClaw**, and **Hermes Agent**. Fully compatible with Windows 11, macOS, and Ubuntu/Linux.

---

## Key Features

### 🔌 Multi-Agent Integrations
- **Claude Code** — Seamless integration via native command hooks and custom HTTP permission hooks.
- **Codex CLI** — Official hook system with JSONL fallback (`~/.codex/sessions/`), registered automatically with custom permission bubbles.
- **Copilot CLI** — Command hooks integrated via `~/.copilot/hooks/hooks.json`.
- **Gemini CLI** — Command hooks via `~/.gemini/settings.json` (auto-registered, or run `npm run install:gemini-hooks`).
- **Antigravity CLI (agy)** — Integrated via `~/.gemini/config/hooks.json` (auto-registered, or run `npm run install:antigravity-hooks`). Note: State-only integration; all Allow/Deny decisions remain inside agy's native terminal menu.
- **Cursor Agent** — [Cursor IDE hooks](https://cursor.com/docs/agent/hooks) in `~/.cursor/hooks.json` (auto-registered, or run `npm run install:cursor-hooks`).
- **CodeBuddy** — Claude Code-compatible command and HTTP permission hooks via `~/.codebuddy/settings.json` (auto-registered, or run `node hooks/codebuddy-install.js`).
- **Kiro CLI** — Command hooks injected into agent configurations under `~/.kiro/agents/`, plus an auto-created `nibbo` agent synced from Kiro's default config.
- **Kimi Code CLI (Kimi-CLI)** — Command hooks configured via `~/.kimi/config.toml` (`[[hooks]]` entries) (auto-registered, or run `npm run install:kimi-hooks`).
- **Qwen Code** — Command hooks via `~/.qwen/settings.json` (auto-registered, or run `npm run install:qwen-hooks`), supporting state tracking and desktop approval bubbles.
- **opencode** — [Plugin integration](https://opencode.ai/docs/plugins) via `~/.config/opencode/opencode.json` (auto-registered) with zero-latency event streaming and permission bubbles.
- **Pi** — Global extension via `~/.pi/agent/extensions/nibbo` (auto-registered, or run `npm run install:pi-extension`).
- **OpenClaw** — State-only plugin integration via `~/.openclaw/openclaw.json` (auto-registered when OpenClaw config exists).
- **Hermes Agent** — [Plugin integration](https://hermes-agent.org/) via the managed plugin directory (auto-registered, or run `npm run install:hermes-plugin`).
- **Coexistence Mode** — Run multiple agents simultaneously; Nibbo monitors and aggregates session state priorities seamlessly.

### 🎭 Animations & Customization
- **12 Animated States** — Idle, thinking, typing, building, subagent groove, multi-subagent juggling, error, happy, notification, sweeping, carrying, and sleeping.
- **Eye Tracking & Physics** — Nibbo's eyes track your cursor in the idle state, accompanied by a dynamic body lean and shadow stretch.
- **Sleep Sequence** — Cycles through yawning, dozing, collapsing, and sleeping after 60s of inactivity; wakes up with a startled wake-up animation upon mouse movement.
- **Click & Interaction Physics** — Double-click to poke the pet, click four times for a flail reaction, and drag-and-drop from any state with pointer capture.
- **Mini Mode** — Drag Nibbo to the right screen edge or right-click to enter Mini Mode. The pet tucks away at the screen border, peeking on hover and executing parabolic jump transitions.
- **Codex Pet Imports** — Easily import Codex Pet zip packages from `Settings` → `Theme`. Nibbo dynamically maps their atlas animations into managed themes.

### 🛡️ Smart Desktop Permission Bubbles
- **Interactive Prompts** — When supported agents request file edits or command executions, Nibbo displays a floating bubble card on your desktop so you don't have to watch the terminal.
- **Quick Actions** — Approve, deny, or configure permanent rules (`Always`) in a single click.
- **Keyboard Shortcuts** — Use `Ctrl+Shift+Y` to Allow and `Ctrl+Shift+N` to Deny active permission bubbles.
- **Smart Stacking & Sync** — Prompts stack cleanly upward from the bottom-right corner and dismiss automatically if answered inside the terminal first.

### 📊 Session Dashboard & HUD
- **Real-Time Monitoring** — Open the Sessions History Dashboard to view active sessions, past tool runs, logs, and system commands.
- **Session HUD** — A glassmorphic overlay containing current session states, times elapsed, and subagent processes.
- **Terminal Focus** — Click on any session in the HUD or Dashboard to instantly focus that agent's terminal window.

### ⚙️ System Features
- **Click-Through Transparency** — Transparent window areas pass clicks straight to the workspace below; only the pet's body registers inputs.
- **Auto-Start & Memory** — Nibbo remembers its coordinates across restarts and can launch automatically when a supported agent session starts.
- **Do Not Disturb (DND)** — Silences sound effects and suppresses permission bubbles (allowing agents to fall back to their native terminal prompts).
- **Sound Design** — Subtle audio alerts for task completions and permission cues (includes a 10s cooldown and auto-mute in DND).

---

## Animations

<table>
  <tr>
    <td align="center"><img src="assets/gif/clawd-idle.gif" width="100"><br><sub>Clawd Idle</sub></td>
    <td align="center"><img src="assets/gif/clawd-thinking.gif" width="100"><br><sub>Clawd Thinking</sub></td>
    <td align="center"><img src="assets/gif/clawd-typing.gif" width="100"><br><sub>Clawd Typing</sub></td>
    <td align="center"><img src="assets/gif/clawd-building.gif" width="100"><br><sub>Clawd Building</sub></td>
    <td align="center"><img src="assets/gif/clawd-headphones-groove.gif" width="100"><br><sub>Clawd 1 Subagent</sub></td>
    <td align="center"><img src="assets/gif/clawd-juggling.gif" width="100"><br><sub>Clawd 2+ Subagents</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="assets/gif/calico-idle.gif" width="80"><br><sub>Calico Idle</sub></td>
    <td align="center"><img src="assets/gif/calico-thinking.gif" width="80"><br><sub>Calico Thinking</sub></td>
    <td align="center"><img src="assets/gif/calico-typing.gif" width="80"><br><sub>Calico Typing</sub></td>
    <td align="center"><img src="assets/gif/calico-building.gif" width="80"><br><sub>Calico Building</sub></td>
    <td align="center"><img src="assets/gif/calico-juggling.gif" width="80"><br><sub>Calico Juggling</sub></td>
    <td align="center"><img src="assets/gif/calico-conducting.gif" width="80"><br><sub>Calico Conducting</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="assets/gif/cloudling-idle.gif" width="120"><br><sub>Cloudling Idle</sub></td>
    <td align="center"><img src="assets/gif/cloudling-thinking.gif" width="120"><br><sub>Cloudling Thinking</sub></td>
    <td align="center"><img src="assets/gif/cloudling-typing.gif" width="120"><br><sub>Cloudling Typing</sub></td>
    <td align="center"><img src="assets/gif/cloudling-building.gif" width="120"><br><sub>Cloudling Building</sub></td>
    <td align="center"><img src="assets/gif/cloudling-juggling.gif" width="120"><br><sub>Cloudling Juggling</sub></td>
    <td align="center"><img src="assets/gif/cloudling-conducting.gif" width="120"><br><sub>Cloudling Conducting</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="themes/dewdrop/assets/codex-pet-idle-loop.svg" width="90"><br><sub>Dewdrop Idle</sub></td>
    <td align="center"><img src="themes/dewdrop/assets/codex-pet-review-loop.svg" width="90"><br><sub>Dewdrop Thinking</sub></td>
    <td align="center"><img src="themes/dewdrop/assets/codex-pet-running-loop.svg" width="90"><br><sub>Dewdrop Typing</sub></td>
    <td align="center"><img src="themes/dewdrop/assets/codex-pet-running-loop.svg" width="90"><br><sub>Dewdrop Building</sub></td>
    <td align="center"><img src="themes/dewdrop/assets/codex-pet-waving-loop.svg" width="90"><br><sub>Dewdrop Groove</sub></td>
    <td align="center"><img src="themes/dewdrop/assets/codex-pet-waiting-loop.svg" width="90"><br><sub>Dewdrop Alert</sub></td>
  </tr>
</table>

For the full state mapping guides and interaction physics, see **[docs/guides/state-mapping.md](docs/guides/state-mapping.md)**.

---

## Quick Start

Download the latest prebuilt installer from **[GitHub Releases](https://github.com/tusharv2005/Nibbo/releases/latest)**:

- **Windows**: `Nibbo-Setup-<version>-x64.exe` or `Nibbo-Setup-<version>-arm64.exe`
- **macOS**: `.dmg` (supports Apple Silicon and Intel)
- **Linux**: `.AppImage` or `.deb`

Launch Nibbo after installation; active agent hooks are configured automatically.

### Running from Source
Run from source to test unreleased integrations or contribute to the project:

```bash
# Clone the repository
git clone https://github.com/tusharv2005/Nibbo.git
cd Nibbo

# Install Node.js dependencies
npm install

# Start the Nibbo Electron application
npm start
```

For advanced setups including Remote SSH servers, Windows Subsystem for Linux (WSL), and platform-specific guides, see **[docs/guides/setup-guide.md](docs/guides/setup-guide.md)** and **[docs/guides/guide-remote-ssh.md](docs/guides/guide-remote-ssh.md)**.

---

## Creating Custom Themes

Nibbo supports custom pet formats. You can create your own character or import packages from **Codex Pet**:
1. Open `Settings` → `Theme` → `Import pet zip` and select any Codex Pet package.
2. To scaffold a theme from scratch, run:
   ```bash
   npm run create-theme -- my-custom-theme
   ```
3. Edit `theme.json` and add your assets (supports SVGs, GIFs, WebPs, APNGs, and PNGs).
4. For detailed field mappings, read the **[docs/guides/guide-theme-creation.md](docs/guides/guide-theme-creation.md)**.

---

## Contributing

Nibbo is community-driven. Bug reports, feature suggestions, and pull requests are highly appreciated. Feel free to open an [issue](https://github.com/tusharv2005/Nibbo/issues) or submit a PR.

### Maintainers & Contributors

<table>
  <tr>
    <td align="center" valign="top" width="140"><a href="https://github.com/tusharv2005"><img src="https://github.com/tusharv2005.png" width="72" style="border-radius:50%" /><br /><sub><b>@tusharv2005</b><br />Developer / Creator</sub></a></td>
  </tr>
</table>

---

## License

Source code is licensed under the [GNU Affero General Public License v3.0](LICENSE) (AGPL-3.0).

**Artwork and bundled theme assets (inside `assets/` and `themes/*/assets/`) are not covered by AGPL-3.0.** All rights reserved by the original creators. See [assets/LICENSE](assets/LICENSE) for details.
- **Clawd** theme artwork inspired by Anthropic.
- **Calico** and **Cloudling** artwork by 鹿鹿 ([@rullerzhou-afk](https://github.com/rullerzhou-afk)).
- **Dewdrop** theme assets.
