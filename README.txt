DHEETI - how to put this app online (free, 5 minutes)

1. Go to https://app.netlify.com/drop (free account) and drag this whole folder onto the page.
2. Netlify gives you a link like https://your-name.netlify.app . Open it on your phone.
3. Android Chrome: menu (3 dots) > Install app.   iPhone Safari: Share > Add to Home Screen.
4. After the first visit, the app also opens with no internet. Everything works offline:
   syllabus, MCQs, mock tests, fresh practice questions, concept notes, notes, reminders, app lock.

Files:
  index.html            the whole app
  manifest.webmanifest  app name, colours and icons (makes it installable)
  sw.js                 offline support + notification support (service worker)
  icon-*.png            app icons

PLANNER (the student chooses: digital, fillable PDF, or paper)
  - planner/ holds a Print PDF (A5, for paper) and a Fillable PDF (type on a phone or tablet) for Foundation, Inter and Final.
  - Inside the app: Menu > Your Planner. It offers Digital (in the app), Fillable PDF and Print PDF. Nothing is forced.
  - A student who wants it digital can: (1) install the app and use My Planner, or (2) download the Fillable PDF and open it in
    any PDF app (Acrobat Reader, Google Drive, Chrome). Both work offline after the first download.
  - A student who wants paper can print the Print PDF (A5, or A4 two-up) or get it spiral-bound at a print shop.

REMINDERS / NOTIFICATIONS
  - Reminders alert you while Dheeti is open or running in the background.
  - Tap "Enable phone notifications" once in Reminders to allow system notifications.
  - For alerts when the app is fully closed you need either Web Push (a small server) or a native
    wrapper with Local Notifications (for example Capacitor). Ask when you are ready for that step.

PRIVACY AND SECURITY (what is true for this build)
  - All student data is saved only on the student's own device. There is no server, account, analytics or AI.
  - A strict Content-Security-Policy (in index.html and in _headers) stops the app from sending data anywhere.
  - _headers is read by Netlify. It also blocks embedding the app in other sites (clickjacking).
  - App Lock: PIN and pattern are stored only as salted PBKDF2 hashes. Wrong tries lock the app for longer and longer,
    and the lock-out survives a reload. The app can lock again after the student leaves it.
  - Students can share a progress report by choosing what to include (WhatsApp, share sheet, copy, .txt).
  - Encrypted backup/restore (AES-GCM with a passphrase) lets a student move to a new phone.
  Honest limits: data is not encrypted while the app is unlocked, so anyone who can open it on an unlocked phone can see it.
  Clearing browser data or uninstalling the app deletes everything unless a backup exists.
  Real accounts, cloud sync and server notifications need a backend (a later step).

Dheeti is made only to help students. It is not affiliated with ICAI.
