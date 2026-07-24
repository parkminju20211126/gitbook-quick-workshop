# STEP 4. Connection — connect external tools

> The tools you connect here become the raw materials for the next STEP. The "morning email summary" agent in STEP 5-1 needs an Outlook connection to run, and lead reports produced by qualify-lead or artifacts from branded-report only complete a real workflow once they're logged and shared through SharePoint.

The more sources you connect, the better Quick understands the context of your work. Start with your communication channels.

---

## ① Open the connections screen

Open **Settings → Capabilities → Connections**. A list of available connectors appears.

---

## ② Connect sources

<table><thead><tr><th width="180">Source</th><th>What Quick learns</th><th width="110">Priority</th></tr></thead><tbody><tr><td><strong>Outlook / Gmail</strong></td><td>Email context, contacts, follow-up threads</td><td>Must</td></tr><tr><td><strong>Calendar</strong></td><td>Upcoming meetings, attendees, prep items</td><td>Must</td></tr><tr><td><strong>Slack</strong></td><td>Team conversations, project context, relationships between people</td><td>High</td></tr><tr><td><strong>Salesforce / AWSentral</strong></td><td>Accounts, opportunities, deal stages, customer data</td><td>High</td></tr><tr><td><strong>Zoom</strong></td><td>Meeting recordings, transcripts, conversation context</td><td>High</td></tr><tr><td><strong>AWS Documentation MCP</strong></td><td>Search official AWS docs directly from Quick chat</td><td>Recommended</td></tr><tr><td><strong>Local Folders</strong></td><td>Documents, presentations, and notes on your computer</td><td>Recommended</td></tr></tbody></table>

**Recommended connection order:**

1. Connect **Outlook (or Gmail)** → approve access
2. Connect **Calendar**
3. Connect **Slack** if you can
4. Add at least one **Local Folder**: **Settings → My Computer → Local Folders → Add**
5. Continue with the remaining High / Recommended connectors as time allows

For each connector, go through OAuth sign-in with your corporate account → grant permissions.

---

## ③ Verify each connector

Run one prompt per connector to confirm it's wired up. If a permission popup appears, click **Allow**.

**Outlook / Calendar**

```
Summarize my calendar for this week. Flag any meetings that need prep separately, and include the recent email threads related to each meeting.
```

**Slack**

```
Find the 3 most active channels I'm in this week and summarize the main discussions in each.
```

**Salesforce / AWSentral**

```
List the opportunities I own that are set to close this quarter, organized by deal stage.
```

**Zoom**

```
Pull out the issues and follow-up actions that came up repeatedly across my Zoom meeting transcripts from last week.
```

**AWS Documentation MCP**

```
Give me a table of the latest supported regions for Amazon Bedrock and which foundation models are available in each.
```

**Local Folders**

```
Find the 3 most recent documents in the folder I just added and summarize each in one paragraph.
```

---

## ④ (Optional) Combine sources

The real power kicks in once you use multiple sources at once.

```
Find the customer meetings in my calendar this week, and for each attendee gather context from recent emails, Slack conversations, and Salesforce account notes — then compile a one-page prep briefing.
```

```
Take the qualify-lead result on the ./call-transcripts/discovery-acme-corp.txt call and save it to a "Lead Reports" subfolder in my local folder as "lead-qualification-hanbit-YYYY-MM-DD.md".
```

> **Tip:** The more connectors you have, the less you need to say "use tool X" in your prompt — Quick figures out which connectors to use on its own.

---

## If something goes wrong

- **Auth failure**: Sign in again with your corporate account. OAuth tokens expire every 90 days.
- **Connector missing from the list**: Ask your org admin to enable it.
- **No data coming through**: Recheck that connector's permission scopes in Settings.

---

> **Next:** [STEP 5. Quick's distinctive features →](step-5-quick-features.md)
