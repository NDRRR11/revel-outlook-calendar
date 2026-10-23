# Test Checklist

Run these checks in a non-production Revel template before relying on the gadget.

## Standalone preview
- [ ] Open `preview.html` in Edge or Chrome.
- [ ] Switch between Weekly and Daily.
- [ ] Confirm Transparent mode shows the preview-only checker pattern behind the text.
- [ ] Switch to Solid color and verify the chosen background color appears.
- [ ] Confirm text, accent color, font family, and font size update.
- [ ] Test all field orders, selecting Date, Time, and Meeting name once each.
- [ ] Test continuous scrolling at 15, 30, 45, 60, and 90 seconds.
- [ ] Confirm no-scrolling mode leaves the list stationary.

## Revel CMS and player
- [ ] Load the XML URL in a test Gadget zone.
- [ ] Verify Revel accepts the gadget definition and displays its user preferences.
- [ ] Confirm transparent mode lets the template background show through.
- [ ] Confirm Solid color fallback works.
- [ ] Test Weekly and Daily in separate instances.
- [ ] Test typography, field order, scroll settings, and refresh interval.
- [ ] Test on the actual player hardware and target display resolution.
- [ ] Check readability over the actual template background.

## Outlook ICS access
- [ ] Confirm calendar publishing is permitted by organizational policy.
- [ ] Test with an approved feed without committing the URL to GitHub.
- [ ] Confirm whether the player/browser can fetch the feed.
- [ ] Validate time zones, recurring events, cancellations, all-day events, and daylight-saving transitions.
- [ ] If blocked, consult IT/security for an approved alternative. Do not disable security controls.
