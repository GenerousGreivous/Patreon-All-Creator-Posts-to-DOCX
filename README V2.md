# All Creator Posts to DOCX (text only)

Compile Patreon posts into a formatted Word document (.docx) for personal offline reading.
Best suited for text-based content such as serialised fiction, essays, and blog series.

NOTE: Text content only. Images embedded in posts are not currently scraped.

================================================================================

## Requirements

- Python 3.8 or higher: https://python.org/downloads
  During install, check "Add Python to PATH"

Install dependencies by running this once in your terminal:

```
pip install requests python-docx
```

================================================================================

## Quick Start

### Step 1 - Get your Patreon cookie string

You must be an active patron of the creator to access their posts.
The script authenticates as you using your browser session cookies.

1. Open Chrome or Brave and log into https://www.patreon.com
2. Navigate to the creator's posts page
   e.g. https://www.patreon.com/c/creatorname/posts
3. Press F12 to open DevTools
4. Click the Network tab
5. In the filter box type: api/posts
6. Press F5 to refresh the page
7. Click the first request that appears in the list
8. In the right panel click Headers
9. Scroll down to Request Headers
10. Find the line starting with "cookie:"
11. Copy the entire value (it is a long string)
12. Paste it as COOKIE_STRING in the script

================================================================================

### Step 2 - Edit the config

Open creator_posts_to_docx.py in any text editor and fill in the CONFIG section near the top:

```python
COOKIE_STRING = "paste_your_cookie_here"
CREATOR_URL   = "https://www.patreon.com/c/creatorname/"
OUTPUT_FILE   = "book.docx"
BOOK_TITLE    = "My Book"
FILTER_TITLE  = ""       # e.g. "Chapter" or "Part" -- leave blank for ALL posts
SORT_ORDER    = "asc"    # "asc" = oldest first (recommended), "desc" = newest first
```

================================================================================

### Step 3 - Run

Windows (Command Prompt):

```
cd C:\path\to\script
python creator_posts_to_docx.py
```

Mac or Linux (Terminal):

```
cd /path/to/script
python3 creator_posts_to_docx.py
```

The script will print progress as it fetches each post, then save the .docx to the path set in OUTPUT_FILE.

================================================================================

## Config Reference

```
Setting        | Description                                              | Example
---------------|----------------------------------------------------------|----------------------------------
COOKIE_STRING  | Your Patreon session cookies from DevTools               | "session_id=abc123..."
CREATOR_URL    | Full URL of the creator's Patreon page                   | "https://www.patreon.com/c/name/"
OUTPUT_FILE    | Path and filename for the output                         | "book.docx"
BOOK_TITLE     | Title shown on the document cover page                   | "My Book"
FILTER_TITLE   | Only include posts whose title contains this text.       | "Chapter"
               | Leave blank for all posts. Case-insensitive.             |
SORT_ORDER     | asc = oldest first / desc = newest first                 | "asc"
POST_DELAY     | Seconds between requests. Do not lower below 0.5         | 0.8
```

================================================================================

## Notes

- Cookies expire after a few days. If you get an authentication error, repeat Step 1 to get a fresh cookie string.
- The script only accesses posts your account can already see. Posts locked to a higher patron tier will be skipped and noted in the output.
- The generated .docx opens with a legal disclaimer page as the first page, followed by a cover page, then the compiled chapters.
- Word counts are printed for each chapter as it fetches so you can confirm it is working.

================================================================================

## Legal Disclaimer

BY USING THIS SCRIPT YOU AGREE TO THE FOLLOWING IN FULL.

This script is provided strictly for personal, non-commercial use by paying patrons,
solely for private reading convenience.

All content retrieved by this script is the exclusive intellectual property of the
original content creator and is protected by copyright law, including the U.S. Copyright
Act (17 U.S.C.), the Digital Millennium Copyright Act (DMCA), and equivalent legislation
worldwide (Berne Convention, EU Copyright Directive, etc.).

================================================================================

### You may NOT:

- Distribute, share, upload, or transmit the output to any other person or platform
- Publish, republish, or post the content online
- Sell, license, or monetise the content in any form
- Use the content for AI training or data harvesting
- Remove or alter any copyright notices
- Create derivative works for distribution

Doing so may constitute civil copyright infringement and/or criminal copyright theft,
punishable by significant fines and/or imprisonment.

================================================================================

### No Circumvention

This script accesses only content your own Patreon account is authorised to view.
It does not bypass, crack, or circumvent any paywall or access control.
Using it to access content beyond your paid tier is strictly prohibited.

================================================================================

### No Warranty

This script is provided "as is", without warranty of any kind, express or implied,
including but not limited to warranties of merchantability, fitness for a particular
purpose, or non-infringement. The entire risk as to quality and performance is with you.

================================================================================

### Limitation of Liability

To the maximum extent permitted by applicable law, the script's author(s), contributors,
and distributors shall not be liable for any direct, indirect, incidental, special,
exemplary, consequential, or punitive damages whatsoever -- including legal fees, fines,
penalties, or claims brought against you by third parties -- arising out of or in
connection with your use or misuse of this script.

================================================================================

### Indemnification

By using this script you agree to fully indemnify, defend, and hold harmless the
script's author(s), contributors, and distributors from and against any and all claims,
damages, losses, liabilities, costs, and expenses (including reasonable legal fees)
arising out of your use of this script or your violation of any third-party rights,
including copyright.

================================================================================

### User Responsibility

You bear sole and complete responsibility for how you use this script and its output,
and for ensuring compliance with all applicable local, national, and international laws.
Ignorance of these terms or applicable law is not a defence.

================================================================================

### Support the Creator

This tool exists to enhance your reading experience, not to undermine the authors
whose work you enjoy. Please continue supporting them directly on Patreon.
If you can no longer afford a subscription, cancel it.
Do not use this tool as a substitute for payment.

================================================================================

## License

This script is released for personal use. See the disclaimer above.
The author(s) of this script claim no ownership over any content retrieved by it.
