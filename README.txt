Apna Booth app v2 - prototype screens (HTML)

Open index.html (or Main.dc.html) in Chrome - double-click works, no server needed. Serve the folder over http for best results, e.g.:
  python3 -m http.server 8000   then open http://localhost:8000

Files
- Main.dc.html        Home (voice banner, family e-slips, service tiles)
- ESlip.dc.html       Digital e-slip with QR, WhatsApp share, read aloud
- Queue.dc.html       Poll day: live queue and route
- Safety.dc.html      Safe Path, CAPF post, SOS
- Chat.dc.html        Sahayak helpline chatbot
- AiVoice.dc.html     Listen & Translate (Hindi, English, Urdu, Bhojpuri, Awadhi, ISL), Braille
- Access.dc.html      Accessibility hub: voice-first, Booth Buddy, sign language help (Access.dc.html#isl)
- Rehearsal.dc.html   EVM + VVPAT ballot rehearsal
- Selfie.dc.html      Voter selfie contest
- RampCheck.dc.html   Rate your booth / Ramp Check
- VoiceNav.dc.html    Speak-to-navigate component used on every screen
- CeoConsole.dc.html  CEO Office console (voter-roll de-duplication), desktop layout
- support.js          Prototype runtime (bundles React); renders the {{ }} placeholders and runs each screen's logic

How each screen is built
- Markup: plain HTML with inline CSS inside <x-dc>.
- {{name}} placeholders, <sc-if> (conditions) and <sc-for> (lists) are filled from renderVals() in the
  <script type="text/x-dc"> block at the bottom of each file (class Component extends DCLogic, React-style state).
- Links between screens are ordinary <a href="X.dc.html">.

Notes for the production build
- Treat these as the design and behaviour reference; rebuild natively (Flutter / React Native / Kotlin / Swift).
- Voice recognition uses the browser Web Speech API (Chrome, mic permission). Text-to-speech uses speechSynthesis.
- Power-button SOS, masked calling, OTP login, WhatsApp Business API, Sarvam speech/translation and roll data are not wired; all data is dummy.
