# Wiki theme

`custom.css` is the master copy of the Vertyco neon-on-dark brand styling.

**It is NOT auto-synced by Wiki.js.** This file is version history / backup only. To apply or update the live look:

1. Open `custom.css`, copy the entire contents.
2. In Wiki.js: **Admin > Theme > CSS Override**.
3. Paste, replacing what's there, and save.
4. Reload the site (hard refresh) to confirm.

The site-wide Organization JSON-LD lives separately in **Admin > Theme > Head HTML** (do not touch it when updating CSS).

To revert the look entirely, clear the CSS Override box.

The hero block and styled cards on the home page use class names defined in this CSS (`.v-hero`, `.v-card`, `.v-chip`, etc.); their markup lives in `home.md`.
