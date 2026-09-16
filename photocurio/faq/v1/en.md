# PhotoCurio Support & FAQ

<!--
Canonical source for user-facing support content, published by
scripts/publish-faq.sh to support.saltairworks.com/photocurio/faq — the App
Store support URL, and the copy the app's Help shows (Settings → Help,
decisions #136–#137). The app also bundles this file for when it is offline.
The published copy wins over the bundled one, so publish changes before
shipping a build that includes them. Comments like this one show nowhere.

The app reads a strict subset of Markdown; FAQDocumentTests fails on
anything else, and the publish script refuses it:
- "## " starts a section and "### " a question; every paragraph and list
  belongs to a question.
- Paragraphs, "- " bullets and "1. " numbered lists (not nested); wrapped
  lines are fine. Inline **bold**, *italic* and `code`.
- No links, images, block quotes, code blocks, tables or rules — an Apple
  TV has nowhere to open a link.
- One tag comment may follow a question on the next line:
  platforms: tvOS (or iPadOS) shows it only on those devices, and
  since: 1.1 only in that app version and later — so a published answer
  about a new feature doesn't reach older installs. Both together are
  separated by a semicolon.
-->

## Getting photos onto the frame

### Do my family members need Apple devices to add photos?

PhotoCurio plays albums from your Apple Photos library, including **iCloud
Shared Albums** — the easiest way for family to add photos to the frame:

- **iPhone, iPad, or Mac**: they accept your Shared Album invitation and add
  photos from the Photos app.
- **Windows PC**: **iCloud for Windows** supports Shared Albums, so Windows
  users can contribute too.
- **Android phones** cannot add to iCloud Shared Albums (there is no Apple
  app for Android, and iCloud.com does not support Shared Albums). See the
  next two answers for ways around this.

### Can PhotoCurio play my Google Photos albums?

Not directly. Google no longer lets apps read your Google Photos library or
albums — apps can only receive photos you pick one at a time in Google's own
picker — so an album on Google Photos cannot stay in sync with the frame.
Two workarounds:

**"Add to Frame" Shortcut (quick, works from the Google Photos app)**

1. On your iPhone, open the Shortcuts app and create a shortcut named
   **Add to Frame** with two actions: *Receive Images from Share Sheet* →
   *Save to Photo Album* (choose or create an album named **Frame**).
2. In the Google Photos app, open the album, select the new photos, tap
   Share, and choose **Add to Frame**.
3. In PhotoCurio, select the **Frame** album. iCloud Photos keeps it in sync
   across your iPad and Apple TV.

You still choose which photos to send, but nothing needs downloading or
re-importing.

**Shared cloud folder + automatic Shortcut (hands-off)**

1. Create a shared folder in Google Drive, Dropbox, or OneDrive (all have
   Android apps) and invite your family to add photos to it.
2. On your iPhone, install that service's app so the folder appears in the
   Files app.
3. In Shortcuts, create an **Automation** that runs daily: *Get Contents of
   Folder* (the shared folder) → *Filter Files* (images, modified in the
   last day) → *Save to Photo Album* (**Frame**).
4. In PhotoCurio, select the **Frame** album.

New photos appear on the frame without anyone touching the iPad.

### Can I favorite a photo from a Shared Album?

No — Shared Albums don't support marking photos as favorites (and their
"likes" are a feature private to the Photos app, with no way for other apps
to send one). The heart button appears dimmed for those photos, and tapping
it explains why. Favorites work
normally for your own albums — and for the iCloud **Shared Photo Library**
(the family library, distinct from Shared Albums), whose photos behave like
your own — and are synced everywhere by iCloud.

### How do I stop one photo in an album from showing?

Hide it. While the photo is on screen, pause the slideshow and choose the
**eye-slash** button under the heart (on Apple TV: press **Up**, then
**Down**, then click). It won't appear in the slideshow again, in any album
you choose. This works for Shared Album photos too, and nothing changes in
your Photos library — the list of hidden photos is kept by PhotoCurio on
that device, so an iPad and an Apple TV each keep their own.

Changed your mind straight away? Choose **Undo** in the "Photo hidden"
message (on Apple TV, press **Up** to reach it, then click). Later, go to
**Settings → Playback → Hidden Photos** and select the photo, or choose
**Unhide All**.

### I have an OLED TV — will PhotoCurio burn in?

PhotoCurio is built to be left running, so it takes this seriously. The
whole overlay layer — clock, heart, caption strip, progress line — drifts
slowly and continuously, a few pixels a minute, so none of it sits on the
same pixels for hours. It happens automatically; there is nothing to turn
on. The background fill behind Fit and Framed photos defaults to **Edge
Gradient**, which changes with every photo rather than holding one flat
colour, and the text colours include Warm White and Soft Gray, both gentler
than pure white.

Three things you can do on top of that, in the order they matter:

- **Use a sleep schedule** so the screen is black overnight — it is free,
  it is offered during setup, and it lives in Settings → Sleep. A frame
  that runs 24 hours is asking much more of a panel than one that runs
  sixteen. "Sleep Now" puts it out by hand any time.
- **Turn on your TV's own pixel shift** (often called Screen Shift, Pixel
  Shift, or Screen Move, usually under picture or panel-care settings),
  along with any panel-refresh routine it offers. It moves the whole
  picture, which no app can do from inside.
- **Prefer a varying background fill** — Edge Gradient or Blur over Black
  — if you show a lot of photos that don't fill the screen.

Modern OLEDs also run their own compensation cycles when you put the TV on
standby, so letting the TV rest is worth more than any single setting.

### Can PhotoCurio wake up when I get home, or react to motion?
<!-- platforms: iPadOS -->

PhotoCurio's Siri actions (Wake, Sleep Now, Play, Play Album, and more) work
in the Shortcuts app's **personal automations on the iPad itself** — the
practical recipes:

- **Wake when you arrive, sleep when you leave** — Shortcuts → Automation →
  New → *Arrive* (or *Leave*) → your home location → add PhotoCurio's
  **Wake** (or **Sleep Now**) action, and choose *Run Immediately*.
- **Play when the frame goes on its stand** — trigger on *Charger
  Connects* → **Play Slideshow**.
- **Your own schedule** — *Time of Day* triggers can drive Sleep Now and
  Wake for a fully custom routine.

One honest limitation: a HomeKit **motion sensor** can't yet trigger app
actions on the iPad — the Home app's sensor automations run on your home
hub, which can't reach apps on other devices. **Presence Detection** (Pro,
iPad) does this job from the frame itself: the front camera notices when
someone is near, entirely on-device, and nothing is recorded or shared.

## Weather, remote control, and Pro

### What do I get with PhotoCurio Pro?

Weather overlays, the browser remote, Smart Framing (the Ken Burns and Fill
styles, which keep faces and pets in frame), and — on iPad —
Presence Detection. One purchase, no subscription, and Family Sharing covers the
household.

Everything a photo frame needs to work unattended is free, including the
**sleep schedule**: the app keeps your device from locking itself, so the
way to make the screen go dark at night is not something we would sell you.

### Why don't I see weather?

Weather is a Pro feature and needs location access (approximate is enough)
and an internet connection. Turn on Current Weather or the Forecast in
Settings → Ticker; both appear in the strip along the bottom of the
screen, taking their turn with today's date and the photo caption.

### How do I pause, skip, or get back to the albums on Apple TV?
<!-- platforms: tvOS -->

Press **Play/Pause** on the Siri Remote (or click the touch surface) to
pause; press again to resume (the show also resumes on its own after 30
seconds). Swipe or press **left/right** to go to the previous or next photo.
Press **Menu/Back** to return to the album list, where pressing Play starts
the show for the selected albums.

### How do I control the frame from my phone?

Turn on Remote Control (Pro) in Settings, then open the address shown there
— or scan the QR code — in any browser on the same Wi‑Fi network. The remote
page offers previous / play-pause / next, a favorite button, and a hide
button for the photo on screen.

The address includes a private link that only devices which have scanned it
know, so other devices on your network can't see or control the frame. If
you've shared it with a device you no longer want controlling the frame, tap
**Reset Remote Link** in Settings → Remote Control and scan the new code.
