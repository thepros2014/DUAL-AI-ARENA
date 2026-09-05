# Navigation bar and battle controls

Use this guide to identify the controls at the top of the Arena and choose the right action during a battle. Labels below were checked against the current application source; older installed releases may look different.

## Global navigation bar

| Item | What it tells you or does | How to use it |
| --- | --- | --- |
| **DUAL AI logo** | Opens the Owner / Manager administration console. | Double-click the logo, then complete first-run setup or sign in. See [[How-To-Access-Admin-Console]]. |
| **FRESH CONTEXT MODE** | Indicates the Arena's focused turn-by-turn workflow. | Read-only indicator; there is no mode switch on this badge. |
| **Edition name** | Identifies the package profile running in the app. | Read-only label. Check the separate activation button for license status. |
| **FREE EVALUATION** or **[edition] ACTIVE** | Opens the package and license activation dialog. | Click to review the edition information or enter your purchased license key. |
| **PLAY-BY-PLAY** | Turns spoken commentary on or off when audio is available. | Click to toggle. See the audio states below. |
| **OpenAI-compatible, Ollama, Gemini badges** | Show each provider's reported state and selected model. | Read these badges to check your setup. Change settings in **PROVIDER CONFIGURATION** on the challenge setup screen. |

### Provider status: OFF, NOT READY, READY

- **OFF**: the provider is disabled in saved configuration.
- **NOT READY**: the provider is enabled but the app has not reported it as configured and usable. Check the selected model and required settings.
- **READY**: the app reports the provider as configured. Confirm it works by completing a small turn; the badge does not prove that a request has succeeded.

The badges themselves are not on/off switches. In **PROVIDER CONFIGURATION**, choose the provider's enable checkbox, select a model you can use, and click **Save provider settings**. See [[How-To-Configure-AI-Providers]].

### Purchase and activation

1. Click **FREE EVALUATION** or the active-edition button.
2. Review the package information. If needed, **OPEN AI BATTLE LICENSE CHECKOUT** opens the configured store.
3. Enter your purchased key in the license field and select **ACTIVATE VERSION**.
4. Wait for the success message and check that the navigation bar reflects activation.

An active installation can also use this dialog to re-enter or update its license key. License keys and administration passwords are separate. Follow [[How-To-Activate-Your-Purchase]] if activation fails.

### Audio states

| Label | Meaning and next step |
| --- | --- |
| **PLAY-BY-PLAY OFF** | Speech is available but switched off. Click to enable it. |
| **PLAY-BY-PLAY ON AIR** | Speech is enabled. Click again to turn it off. |
| **SIDELINE OFFLINE** | The local commentator model is unavailable. Check Ollama and the commentator setup. |
| **AUDIO UNAVAILABLE** | Audio output or a suitable installed voice is unavailable. Hover over the control for the reason; visual run information remains available. |

See [[How-To-Enable-Live-Radio-Commentary]] for a short audio walkthrough.

## Controls above an active battle

These controls appear beside the challenge heading after a challenge is created.

| Control | Effect | When to use it |
| --- | --- | --- |
| **AUTO HANDOFF OFF** | Automatic turn progression is disabled. | Review each result and start the next turn manually. |
| **AUTO HANDOFF READY** | Automatic handoff is enabled and ready. | Let the Arena advance when a turn can start. Enabling it during an idle battle can start work immediately. |
| **AUTO HANDOFF ON AIR** | Automatic progression is running. | Monitor the current turn and incoming results. |
| **Stop auto handoff** | Requests a stop to the automatic sequence. | Stop scheduling further turns, then check the run state before acting again. |
| **Refresh state** | Reloads the current challenge state. | Update the display when it appears stale; it does not start a new battle. |
| **Wipe / keep copy** | Ends the active run and keeps its Arena-managed working copy. | Finish a run while retaining that working copy. Read the confirmation before proceeding. |
| **Wipe / delete copy** | Ends the active run and deletes its Arena-managed working copy. | Remove a practice run's working copy after saving anything you need. Read the confirmation before proceeding. |

### Stop and inspect a running battle

1. Select **Stop auto handoff** when it is shown, or turn automatic handoff off.
2. Select **Refresh state** and check whether a turn is still processing.
3. Review the latest available result before starting another turn or ending the run.

Stopping automatic handoff is not a rollback. Do not assume a request already sent to a provider has been undone or that prior usage has been refunded.

### Understand the two wipe options

Both options return you to challenge setup after a successful wipe. The app's confirmation states that **Wipe / delete copy** removes only the managed Arena copy; the original imported folder and saved review logs remain. It is not a command to erase every record of the battle.

Copy or export results you need before deleting the working copy. Use [[Viewing-and-Exporting-Results]] for result handling.

## Practice the controls

Create the sample challenge in [[Tutorial-Your-First-Arena-Battle]]. Check provider readiness, keep automatic handoff off, complete one turn, and use **Refresh state**. Then open the administration console, inspect the saved turn, and select **Lock console** when finished. Try wipe controls only on a practice run whose contents you no longer need.

[[Arena-Tutorials]] · [[Home]] · [[How-To-Access-Admin-Console]]
