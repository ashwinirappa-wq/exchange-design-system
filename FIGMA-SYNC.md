# Syncing Tokens from Figma Desktop

Follow these steps to extract actual design tokens from the XDS Figma file into `tokens.css`.

---

## Prerequisites

1. **Figma Desktop App** installed (not the browser version)
2. **Figma MCP plugin enabled** in Cursor:
   - Open Cursor → Settings → MCP
   - Confirm `plugin-figma-figma` is listed and enabled
   - The plugin talks to the Figma desktop app directly

---

## Step-by-Step

### 1. Open the XDS file in Figma Desktop
Open: https://www.figma.com/design/S5vzHnfEkTU1uETKnVOl7x/XDS---Exchange-Design-System

Make sure you open it in the **desktop app**, not in a browser tab.

### 2. Select a layer
Click on any component, colour swatch, or frame in the file.  
You must have a layer visibly selected (highlighted in blue) in the Figma layers panel.

### 3. Ask Cursor to extract tokens
In Cursor chat, paste this prompt:

```
The XDS Figma file is open in Figma Desktop with a layer selected.
File key: S5vzHnfEkTU1uETKnVOl7x
Node ID: 3348:31706

Please:
1. Call get_variable_defs to extract all design tokens
2. Call get_design_context to extract component styles
3. Update tokens.css with the actual values from Figma
4. Note any differences from the current token values
```

### 4. Commit the updated tokens
```bash
git add tokens.css
git commit -m "Sync design tokens from Figma XDS — $(date +%Y-%m-%d)"
git push origin main
```

---

## Rate Limits

| Seat type | Calls per month |
|---|---|
| View / Collab | 6 / month |
| Full / Dev (Org plan) | 200 / day |
| Full / Dev (Enterprise) | 600 / day |

> The account `ashwin.irappa@crypto.com` is currently on a **View seat** (6 calls/month).  
> To increase limits: upgrade to a Full or Dev seat on the Org plan in Figma settings.

---

## Brand Playbook Note

The Brand Playbook is a **Figma Slides** file, which the MCP cannot read directly.  
To access it, open the file manually and review:
- Colour palette
- Typography specifications  
- Logo usage rules
- Tone of voice

Then update `tokens.css` manually with any values from the playbook.

URL: https://www.figma.com/slides/Oyb9M17fbUWZl4C7ZTO3jQ/Exchange-Brand-Playbook
