# Revel Outlook Calendar Gadget

A prototype repository for a custom Revel Digital gadget that displays a published Outlook calendar feed (ICS) in two independently configured instances.

- **Weekly schedule:** rolling date range, configurable scrolling.
- **Daily notices:** today's events with a more prominent text layout.
- **Transparent-first appearance:** transparent is the default; a solid background remains available as a fallback.
- **Standalone preview:** fictional sample meetings and controls for testing layout without Outlook access.

## Repository contents

- `calendar-gadget.xml` - Gadget XML definition, Revel user preferences, styles, and calendar logic.
- `preview.html` - self-contained browser mockup with sample events and appearance controls.
- `TESTING.md` - pre-deployment test checklist.
- `.gitignore` - basic repository exclusions.
- `LICENSE` - MIT license for this prototype.
- `README.md` - setup, publishing, and limitations.

## Quick preview

1. Download or clone this repository.
2. Open `preview.html` in Edge or Chrome.
3. Choose Weekly or Daily, then adjust typography, colors, field order, and scroll timing.
4. Set **Background style** to **Transparent** to preview a transparent gadget. The checker pattern is a preview-only aid showing where the template background would be visible.
5. Choose **Solid color** to preview the fallback background.

The standalone preview uses fictional events only. It does not contact Outlook or load an ICS URL.

## Publish through GitHub Pages

1. Create a repository, for example `revel-outlook-calendar`.
2. Upload the repository files to the root of the repository.
3. In GitHub, open **Settings → Pages** and publish from the `main` branch and `/ (root)` using the available Pages settings.
4. After publishing, the preview is typically available at:
   `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`
5. The gadget XML is typically available at:
   `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/calendar-gadget.xml`
6. In Revel, add a Gadget zone to a **test template** and use the XML URL as the Gadget source.
7. Create two instances from the same XML source:
   - Weekly: `displayMode = Weekly schedule`
   - Daily: `displayMode = Daily notices`
8. Configure each instance independently. Enter the published Outlook ICS URL only after you have confirmed the feed is approved for use and accessible from the Revel player.

GitHub Pages URLs depend on your GitHub username, repository name, and Pages configuration.

## Suggested settings

### Weekly instance
- Display mode: Weekly schedule
- Days to display: 7
- Scroll behavior: Continuous vertical scroll
- Scroll cycle duration: 30 seconds
- Background style: Transparent
- Fields: Date, Time, Meeting name

### Daily instance
- Display mode: Daily notices
- Scroll behavior: No scrolling, unless there are enough notices to require it
- Background style: Transparent
- Choose text and accent colors that remain readable over the template background.

## Security and calendar-feed notes

- Use a published ICS URL only if your organization's Microsoft 365 policy permits calendar publishing.
- Treat the ICS URL like a secret link. Anyone who obtains it may be able to read the calendar details exposed by that feed.
- **Do not commit the ICS URL to a public repository**, issue, screenshot, or documentation file.
- The gadget uses browser-side `fetch`. Cross-origin restrictions (CORS), network policy, or the Revel player environment may block access to the feed.
- Do not disable security controls to work around a failed request. If access fails, investigate an approved alternative with your IT/security team.
- This prototype is not a complete RFC-compliant calendar engine. Time zones, recurring events, cancellations, all-day events, and daylight-saving transitions need validation against the real feed.

## Known limitations and status

- The XML structure is a prototype based on the standard Gadget XML format. It has not been confirmed on your specific Revel CMS/player hardware.
- XML parsing and local preview behavior can be checked independently, but **successful ICS access and Revel rendering must be tested in your environment**.
- The field-order dropdowns allow choosing each field, but the Revel UI does not enforce uniqueness. Select Date, Time, and Meeting name once each.
- The preview checker pattern is only a visual aid. The gadget itself remains transparent when Transparent is selected.
- Test on the actual player and screen before operational use.
