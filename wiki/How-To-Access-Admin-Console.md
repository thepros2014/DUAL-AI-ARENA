# Administration console: access, passwords and features

Create Owner and optional Manager credentials, inspect saved turns, and choose the review information visible in the console. These instructions were checked against the current application source; older releases may differ.

---

## 🔑 1. Unlocking the Administrative Console

Double-click the **DUAL AI logo** at the top left of the Arena to open the **operator console**. You can also use **Ctrl + Shift + A** while the Arena has focus. Opening the dialog does not sign you in: complete Owner setup on first use, or enter an existing Owner or Manager password.

For a tour of the other top-bar functions, see [[Navigation-and-Battle-Controls]]. If these controls are unavailable in your installed edition, contact [product support](mailto:thepros2014@gmail.com?subject=DUAL-AI-ARENA%20Admin%20Console%20Support).

---

## 2. Create your administration passwords

These steps match the current application source; labels may differ in older releases. The panel calls itself the **operator console** or **OWNER / MANAGER CHANNEL**.

1. On **FIRST RUN / OWNER SETUP**, find **Set the control password**.
2. Enter a new password in **OWNER PASSWORD / 8+ CHARACTERS**.
3. To create a separate Manager credential, enter a different password in **MANAGER PASSWORD / OPTIONAL**. Otherwise leave it blank.
4. Each supplied password must contain at least eight characters. Use unique passwords and save them in your password manager.
5. Select **CREATE LOCAL CONTROL CHANNEL**.
6. Confirm that the console opens with an authenticated Owner session.

There is **no default password**. These credentials are separate from your purchase license key and provider API keys. Do not use those keys as passwords.

The Manager credential is a separate sign-in, not a guarantee of reduced permissions. Both authenticated roles can use the current console's display settings and review tools.

## 3. Verify sign-in

1. Select **Lock console**.
2. At **Owner or Manager sign-in**, enter your password in **OWNER / MANAGER PASSWORD**.
3. Select **ENTER CONTROL CHANNEL**.
4. Check the authenticated role displayed in the console.

If you created a Manager password, repeat the check with that credential. If you see sign-in instead of first-run setup, credentials already exist for this installation.

## 4. Select a run and saved turn

Complete a turn using [[Tutorial-Your-First-Arena-Battle]], then open the console.

1. In **RUN INSPECTOR**, select an available saved review.
2. Check the run title and the selected saved turn before interpreting its contents.
3. Read **overview**, then use **transcripts** and **handoff** to examine that saved turn. The **events** tab shows the current run's live event history, rather than a historical timeline tied to the selected saved turn.
4. Expand an individual record or file to read its contents. Change the review selection to inspect another available turn.

If the panel is waiting for an active run, start a match. If no saved turn is available, allow a turn to complete and check again. Display controls change visibility; they do not remove saved information or change provider budgets.

Review records may contain your source code and inputs. Check screenshots and excerpts before sharing them.

## 5. What each inspector tab contains

| Tab | What to look for | Useful question |
| --- | --- | --- |
| **overview** | Turn, team, batches, handoff state, team report and findings. | Which turn am I reviewing, and was its handoff released or held? |
| **transcripts** | Provider/model cards, recorded inputs and responses, concise summaries, available tool records and estimated input usage. | What did each provider receive and return for this turn? |
| **handoff** | Captured team messages, changed files, saved source, findings artifacts, and records identifying which provider/model produced an artifact. | What was passed to the next team, and where did a proposed change come from? |
| **events** | Recent live activity for the current run. | What is happening now, and what was the latest reported event? |

**RELEASED** means the handoff was released to the next team. **HELD** means it was not released; read the report and verification information for context. Neither status independently proves that the code is correct.

Only records captured for that review can be shown. An empty section can mean that no corresponding content was saved, not that the app has failed.

## 6. All eight display settings

Under **DISPLAY CONTROLS**, change one switch and wait for **SAVING** to finish. A switch's **ON/OFF** label shows its current display setting.

| Setting | What it shows | Where to look |
| --- | --- | --- |
| **Prompt and source context** | Recorded instructions and source context supplied for a batch. | **transcripts**: expand the prompt records. |
| **Provider transcripts** | The captured provider response. | **transcripts**: inspect each provider card. |
| **Reasoning summaries** | Concise model explanations and the team report. These are returned summaries, not hidden private reasoning. | **overview** and **transcripts**. |
| **Workspace tool calls** | Captured search, read, and validation tool records, when present. | **transcripts**: inspect tool-call entries. |
| **Generated file content** | Changed files, saved source snapshots, findings artifacts and artifact attribution. | **handoff**: expand a file or inspect its attribution. |
| **Team huddle messages** | Captured messages exchanged during the team handoff. | **handoff**: read the conversation. |
| **Live event history** | Recent activity for the active run. | **events**. |
| **Usage and batch metrics** | Estimated input tokens and size for provider batches. | **transcripts**: read the input estimates on each card. |

These settings govern display in this console. They do not remove stored records, revoke another role's access, configure AI providers, or set spending limits. Input estimates are not a provider billing statement, and some basic turn/batch information remains visible in the overview.

### Practice: trace one proposed change

1. Select a completed practice turn in **RUN INSPECTOR**.
2. In **overview**, identify a finding or the team's stated next focus.
3. In **transcripts**, enable **Provider transcripts** and **Reasoning summaries**, then read the relevant provider's output.
4. In **handoff**, enable **Generated file content** and **Team huddle messages**. Expand a changed file and read its associated conversation or attribution if captured.
5. Compare the proposed change with the finding. Continue with [[Tutorial-Review-and-Test-a-Patch]] to verify behavior outside the console.
6. Turn a display switch off, then back on, to confirm how it affects the view without deleting the record.

## 7. Lock or close the console

Select **Lock console** when finished to end authenticated access. The **×** at the top right closes the panel and returns to the Arena; closing alone does not sign you out. After locking, reopen the console and confirm that it asks for a password.

## Troubleshooting passwords

| Problem | Next step |
| --- | --- |
| Setup button is unavailable | Supply an Owner password of at least eight characters and wait for any active request to finish. |
| Manager password is rejected during setup | Supply at least eight characters or leave the optional field blank. |
| Sign-in fails | Check Caps Lock and accidental spaces. Use the local Owner or Manager password. |
| Setup screen is missing | Setup has already been completed. Use the existing credentials. |
| A review section is hidden | Check its display switch and wait for saving to finish. |
| A review section has no entries | Select a completed turn and check whether that kind of record was captured. |
| Events do not match the selected old turn | Events show current live activity; use the other tabs for saved-turn records. |
| Forgotten password or password change needed | Contact support for your installed version. The current console has no password-change or self-service recovery screen. |

Never include your password in a support request. Provide your app version and a sanitized description of the issue.

**Complete:** you have created your credentials, verified sign-in, reviewed a turn, and locked the console.

[[Arena-Tutorials]]

---

- [[Home]] • [[How-To-Troubleshoot-Common-Errors]] • [[Architecture-and-Security]]
