# Review-Weekly-Report-Automation-Agent
🧠 Review & Weekly Report Automation Agent

This n8n workflow automatically generates review summaries and weekly performance reports using AI, fetches data from Google Sheets, builds a formatted HTML report, stores it, and emails it to the user.

It has two execution modes:

Manual Trigger (upper flow) → For instant review generation

Scheduled Trigger (lower flow) → For automated weekly reporting

📌 Workflow Summary

This workflow performs:

✔ Fetching tasks, logs, or review content from Google Sheets
✔ Sending it to AI for summarization, insights, and report generation
✔ Generating professional HTML reports
✔ Saving reports to Google Drive
✔ Emailing the user with reports attached
✔ Fully automated weekly scheduling

🧩 FULL NODE-BY-NODE EXPLANATION
🔶 TOP WORKFLOW — Instant Review Generation
1. Manual Trigger — “When Clicking Execute Workflow”

This node allows you to manually run the workflow anytime.

Useful for:

On-demand reviews

Quick AI summaries

Testing

2. Getting Record (Google Sheets – Read Sheet)

This node fetches the data that the AI must review.
Examples:

Work logs

Daily entries

Task descriptions

Performance notes

3. AI Agent (Google Gemini Chat Model)

This node takes your sheet data and generates:

Summary

Analysis

Key insights

Recommendations

Positive and negative highlights

Final professional review document

It uses AI Agent node with Google Gemini model for natural, human-like output.

4. Wait Node

Adds a delay before sending the email.

Useful when:

You want to avoid sending multiple emails too fast

You want to delay the report delivery for a scheduled time

5. Gmail – Send Message

Final email is sent to you or the team.

It includes:

The AI-generated review summary

A message body

Optional attachments (if needed)

This completes the manual review report generation flow.

🔶 BOTTOM WORKFLOW — Automated Weekly Reporting
1. Schedule Trigger

Runs automatically on your chosen schedule:

Weekly

Daily

Monthly

Perfect for automated weekly performance reporting.

2. Get Rows (Google Sheets – Read Sheet)

Fetches multiple rows from your Google Sheet such as:

Tasks completed this week

Targets achieved

Pending tasks

Important notes

This becomes the input for the weekly report.

3. JavaScript Code Node

Used for formatting & cleaning:

Filters data (example: only current week)

Converts rows into readable lists

Structures data for HTML

Prepares final clean report content

This ensures only the required weekly data is processed.

4. HTML Template Node

Transforms the AI output + processed data into a styled HTML report.

The HTML report includes:

Title

Sections

Tables

Lists

Highlights

Weekly summary

This allows you to create professional-looking reports for clients or internal teams.

5. Create File (Google Drive – From Text)

The generated HTML report is saved as a file on Google Drive.

Usually saved as:

.html

.txt

.pdf (if later converted)

This makes the report accessible anytime.

6. Gmail – Send Message

Sends the weekly report to your email automatically, with:

HTML report attached

Summary message

Highlights

This completes the weekly automation cycle.

🎯 Final Output of This Workflow

You get:

✔ AI-generated daily or weekly reports
✔ Automatic email delivery
✔ Professional HTML format reports
✔ Google Drive saved archive
✔ Zero manual effort required

This workflow turns your Google Sheet data into real, usable weekly insights.
