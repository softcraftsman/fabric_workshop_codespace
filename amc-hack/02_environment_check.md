---
layout: default
title: "Environment Check"
---

# Environment Check

**Goal:** Confirm that every tool works before the labs start. Most delays in
workshops come from sign-in and access problems, so we find them now.

**Time:** about 10 minutes.

## Checklist

Complete each item. If one fails, raise your hand before continuing.

1. **Open your Codespace** using the link from your facilitator and wait for
   the terminal to finish setting up.
2. **Sign in to Fabric** with the account provided for the workshop. Open
   [app.fabric.microsoft.com](https://app.fabric.microsoft.com) in your browser
   and confirm you reach the home page.
3. **Find your team workspace.** In the workspace list, open the workspace named
   for your team (for example `AMC Readmissions`). You should have
   Contributor access.
4. **See the shared data.** Confirm you can browse `GoldLakehouse` in the
   **AMC Data Engineering** workspace and see the `conformed` and `quality` schemas.
5. **Confirm Copilot in Fabric.** Create a new notebook in your team workspace
   and confirm the **Copilot** button appears on the ribbon.
6. **Confirm Copilot CLI.** In the Codespace terminal, start Copilot CLI and
   ask it a simple question, such as "What folder am I in?"

## Expected result

You can open Fabric, see your team workspace and the shared Gold data, see
Copilot in a notebook, and get an answer from Copilot CLI.

## If you get stuck

| Symptom | Try |
|---|---|
| Cannot sign in to Fabric | Use a private browser window and the workshop account, not a personal one |
| Workspace is missing | Ask the facilitator to confirm your group membership |
| No Copilot button | Tell the facilitator; the capacity or tenant setting may need attention |
| Copilot CLI not responding | Re-run the sign-in prompt in the terminal |

## Safe practices

- Never paste passwords, keys, or real patient data into Copilot.
- Commit your work to Git in your team workspace folder, not the shared
  workspaces.

**Next:** [03 Architecture](03_arch.html)
