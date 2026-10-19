# Pylerium Studio

<img src="assets/icons/pylerium-logo.png" alt="Pylerium logo" width="100">

**Free public beta · Windows · Python source release**

Build, run, inspect and showcase projects in a local developer workbench. Pylerium combines Python execution, a Devcord project explorer, opt-in plugins, model tools, Scene Studio and a video editor in one workspace.

![Pylerium desktop workspace](images/current/lobby.png)

## Get started

Python 3.10 or newer is required; Python 3.13 is recommended for Windows executable builds.

```powershell
git clone https://github.com/Pylerium/PyleriumStudio.git
cd PyleriumStudio
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m playwright install chromium
.\.venv\Scripts\python.exe orchestration-menu.py
```

Webpage capture uses Playwright Chromium. Recording, media conversion and MP4 export require `ffmpeg` and `ffprobe` on PATH. GitHub Engine requires [Git](https://git-scm.com/downloads) and [GitHub CLI](https://cli.github.com/). This update publishes source; it does not include a newly built executable.

## Updated Workshop and Devcord

Import a folder, ZIP, individual files or dropped directories. Explore code, profiles, dependencies and media; edit files; and run Python scripts, Python packages, Flask apps or standalone HTML pages. Native imports stream in the background without an artificial file-count cap.

- Flask preserves the configured port unless it is occupied. HTML entries launch a local Flask server for relative CSS, JavaScript, modules, fonts and graphics, then open **# preview**.
- Interactive Python programs receive input through **# console**. Output is bounded and streamed; Stop owns the complete child-process lifecycle.
- Media plays inside the embedded viewer. Supported conversions run in the background, retain the same player and support seeking.
- Imported Python projects integrate with Arsenal, execution loadouts, existing editors and explicit EXE builds.

| Devcord workspace | Running HTML preview |
| --- | --- |
| ![Devcord profile and file navigation](images/current/devcord-workspace.png) | ![Live HTML and canvas preview](images/current/html-preview.png) |

## Phone access and a roomier layout

Open **Workshop Tools → PHONE QR CODE**, enable sharing and scan from a phone on the same local network. Select the workspace or a project, copy an address, or open connection help. Running HTML and Flask previews use LAN gateways while their existing desktop ports remain unchanged. Sharing is off by default; turning it off closes phone listeners and leaves desktop projects running.

Phone access permits editing and running projects on the computer. Only enable it on a trusted network. Ordinary HTTP and streamed responses are supported; WebSocket forwarding is not currently supported. External CDN resources require internet access.

**Hide Navigation**, **Ctrl+Shift+N**, the global **View** menu and Devcord's **Layout** menu let you reclaim space without removing pages. Narrow phone layouts hide side panels by default and let navigation open over the preview.

| Connection controls | Phone-sized preview |
| --- | --- |
| ![Devcord phone connection dialog with sharing off](images/current/phone-connection.png) | <img src="images/current/mobile-preview.png" alt="Devcord preview at a phone viewport" width="260"> |

## Scene Studio and video editing

The **Showcase** workspace includes local scene creation, 40 vertical scene presets, project/web/plugin capture, model and camera tools, recording and optional phone sharing. Edit Studio adds timeline editing, layouts, cropping, motion, captions, callouts, audio and export tools. The integrated runtime lives in `showcase_studio/`; `python sync_showcase.py` validates it.

| Scene Studio | Edit Studio |
| --- | --- |
| ![Scene Studio with a fresh scene](images/current/scene-studio.png) | ![Edit Studio timeline and tools](images/current/video-editor.png) |

[Showcase guide](SHOWCASE_INTEGRATION.md) · [Scene Studio](showcase_studio/SHOWCASE.md) · [Vertical scenes](showcase_studio/VERTICAL_SCENES.md) · [Video editing](showcase_studio/VIDEO_EDITOR.md)

## Plugins and GitHub Engine

Enable plugins explicitly through **Workshop → Editor & Build Tools → Plugins**. The release includes 15 starter tools plus Jumpback, Ultimate Terminal, cellular automata, Prompt Hub, API Hub and **GitHub Engine**. Extensions can add pages, actions, project templates, execution hooks and reusable commands. Disabled plugins retain their source.

GitHub Engine provides repositories, issues, planning lanes, pull requests, Actions, draft releases, milestones, history, GitHub Projects and local Git tools. Operations run through bounded asynchronous queues with cancellation and timeouts. Repository changes require an explicit action; there is no automatic push, merge or publication. Authenticate with `gh auth login`, environment credentials, or a session-only token. Credentials are not shipped with this release.

The refreshed GitHub Engine uses a clear view sidebar, recent repository history, selection-preserving refresh, filtered row counts and identifier copying. Local checkout tools and the activity log collapse independently to give the current view more space.

| Plugin tools | GitHub Engine |
| --- | --- |
| ![Plugin builder and installed extensions](images/current/plugins.png) | ![GitHub Engine before connecting an account](images/current/github-engine.png) |

API Hub now combines DEV.to drafts/publishing, paginated GitHub insights and a Discord bot/webhook workspace. Discord includes guided server, channel, message, role, moderation, thread, invite, event, command and webhook tools, a message/embed builder, streamed attachments, searchable results and redacted exports. Advanced REST supports additional bot API operations. Live Gateway events, voice/video and command handlers remain responsibilities of your bot service.

| API Hub | Discord workspace |
| --- | --- |
| ![API Hub service tabs and DEV.to publisher](images/current/api-hub.png) | ![Discord operation browser and message builder](images/current/discord-workspace.png) |

Open **Connections** to apply credentials. Keys are session-only by default; remembering them explicitly saves unencrypted local JSON. Requests are asynchronous, bounded, cancellable and rate-limit aware. Discord changes require confirmation and the bot's granted permissions.

[Plugin API and lifecycle](PLUGINS.md) · [Starter collection](STARTER_TOOLS.md) · [API Hub and Discord guide](plugins/dev_blogpost/README.md) · [GitHub Engine setup and operation](plugins/github_engine/README.md)

## Execution, models and creative tools

Arsenal execution loadouts configure interpreters, arguments, companion scripts, environment files, diagnostics and workflows. **Run Project** executes a project; **Build EXE** is a separate operation. Assets provides model inspection and removable assignments. Workshop templates include creative simulations, reusable UI elements and editable boilerplates. Console, Barracks and the Killchain command bar connect live output, history, search and project actions.

Images and 3D models are independent assignments. In **Assets → Card artwork**, or a card's right-click **Card artwork** menu, choose **Automatic**, **Assigned image** or **Assigned 3D model**. Automatic prefers the image when both exist. The live preview and inspector continue showing the assigned model regardless of the card choice. Removing an image preserves the model; removing a model preserves the image.

| Image on the card, model in the preview | Independent model inspector |
| --- | --- |
| ![Execution loadout showing its image and independent model preview](images/current/loadout-artwork.png) | ![Model inspector retains the assigned model and materials](images/current/model-inspector.png) |

## Screenshots

These images were captured from fresh local workspaces using sample HTML and generated demo artwork/models. No personal projects, account data, private media or active phone address were used. The phone image shows Chromium at a phone-sized viewport.

<details>
<summary>All desktop workspaces and compact navigation</summary>

| Workspace | Workspace |
| --- | --- |
| ![Execution loadouts](images/current/loadouts.png) | ![Operators](images/current/operators.png) |
| ![Maps and workflows](images/current/maps.png) | ![Missions and schedules](images/current/missions.png) |
| ![Arsenal project execution](images/current/arsenal.png) | ![Console](images/current/console.png) |
| ![Barracks execution history](images/current/barracks.png) | ![Assets and model tools](images/current/assets.png) |
| ![Settings](images/current/settings.png) | ![Collapsed navigation](images/current/compact-navigation.png) |

</details>

## Privacy and release contents

Local projects, databases, clipboard/activity history, captures, recordings, tokens, plugin account settings, virtual environments and build output are excluded. `.gitignore` protects generated local data; executable builds stage shipped plugins without saved configuration files or caches. A fresh workspace is created on first use in `orchestration_data/`; use `PYLERIUM_HOME` to choose another location. Jumpback/activity and clipboard collection can retain sensitive local information when enabled; manage them in their respective controls.

[Release notes and validation](RELEASE_NOTES.md) · [Source file checksums](RELEASE_MANIFEST.json) · [MIT license](LICENSE)

## Build and verify

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements-build.txt
.\.venv\Scripts\python.exe build_exe.py --onedir --no-icon-picker
.\.venv\Scripts\python.exe -m unittest discover -s . -p "test_*.py"
```

For a portable distribution, package the complete folder build with `release_package.py`; see [Build verification](BUILD.md#verification). Browser checks are opt-in: set `PYLERIUM_BROWSER_TESTS=1` with Playwright Chromium installed. FFmpeg and optional Node-based checks require their respective tools.

[Operations](OPERATIONS.md) · [Workshop](WORKSHOP.md) · [Plugins](PLUGINS.md) · [Build guide](BUILD.md)
