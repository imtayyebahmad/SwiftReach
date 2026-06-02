Screenshot 2026-06-03 015855.png# SwiftReach

SwiftReach is a simple, browser-based WhatsApp outreach dashboard for sending personalized messages from a contact list. It is designed for fast follow-ups, light CRM-style workflows, and small team outreach campaigns.

## Features

- Import contacts from CSV
- Add contacts manually
- Automatically skip duplicate names or phone numbers during sync
- Clean dark-mode UI built with Tailwind CSS
- Personalize messages with variables like `{{name}}` and `{{phone}}`
- Generate WhatsApp Web links using the `wa.me` format
- Open messages one at a time with a sequential "Next" flow
- Track follow-up status with badges:
  - `Not Sent`
  - `Queued`
  - `Sent`
- Mobile-responsive layout

## How It Works

1. Upload a CSV file or paste contacts manually.
2. Review the contact table and select the people you want to message.
3. Write a message template using variables like `{{name}}`.
4. Click **Send Personalized Messages** to build the queue.
5. Click **Open Next in WhatsApp** to open each message sequentially in WhatsApp Web.
6. After opening a chat, mark the follow-up as sent and move to the next contact.

## CSV Format

SwiftReach works best with a CSV that includes a name and phone column, for example:

```csv
Name,Phone
John Doe,+923001234567
Jane Smith,+923009998888
```

It also supports sheet exports that contain extra columns such as `Address`, `Website`, or `Maps URL`. The app will look for the `Name` and `Phone` fields and ignore the rest.

## Phone Number Handling

The app normalizes phone numbers before generating WhatsApp links:

- Removes symbols, spaces, and formatting characters
- Converts local numbers starting with `0` using the default country code
- Converts numbers starting with `00` into international format
- Skips invalid or too-short numbers

If your contacts are from Pakistan, the default country code is set to `92`.

## Duplicate Protection

When syncing contacts from a CSV or manual input, SwiftReach automatically skips duplicates by:

- Matching normalized contact names
- Matching normalized phone numbers

This helps prevent repeated entries when importing the same sheet more than once.

## Message Variables

You can use the following variables in your message template:

- `{{name}}` - Inserts the contact name
- `{{phone}}` - Inserts the normalized phone number

Example:

```text
Hi {{name}}, just checking in regarding your request.
```

## Running Locally

This project is a static front-end app. To run it locally:

1. Open `index.html` in your browser.
2. Or serve the folder with any local static server.

Example:

```bash
npx serve
```

Then open the local URL shown in the terminal.

## Tech Stack

- HTML
- JavaScript
- Tailwind CSS via CDN

## Notes

- This tool opens WhatsApp Web links in sequence rather than sending messages automatically.
- You still need to confirm each message in WhatsApp Web.
- The app is intended for lightweight outreach and follow-up workflows.

## Project Structure

```text
SwiftReach/
├─ index.html
└─ README.md
```

## License

Add a license if you plan to publish or share the project publicly.
