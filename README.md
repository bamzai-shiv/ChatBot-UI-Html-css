Nova Chat 🤖✨
A sleek, glassmorphic web chatbot built with plain HTML, CSS, and JavaScript featuring dark/light themes, neon accents, typing animation, and optional voice features.
Designed for modern, Gen Z‑leaning aesthetics with smooth UX, no build step, and easy API wiring for real responses.

Features 🚀
Glassmorphism card UI with subtle blur, soft shadows, neon ring accents, and custom scrollbars for a premium feel.​

Dark/light theme via CSS custom properties for fast theming and palette swaps.​

Optional text‑to‑speech (TTS) using the Web Speech API’s SpeechSynthesis for spoken replies.​

Best‑effort speech recognition button using browser SpeechRecognition where available.​

Typing indicator, enter‑to‑send, Shift+Enter newline, and auto‑scroll for smooth conversational flow.

Slash commands: /help, /clear, /export for quick utilities and data portability.

Drop‑in API adapter: replace one function to connect any LLM or REST backend.

Demo Setup 🧪
Save the provided code as index.html.

Open index.html in a modern browser that supports backdrop‑filter and the Web Speech API.​

Toggle the theme, type a message, hit Enter, and try the speaker/mic buttons if your browser supports them.​

Project Structure 📁
Single‑file implementation for easy drop‑in embedding: index.html with inline CSS and JS for fast prototyping.

No bundlers or dependencies required; add your own backend when ready.

Theming 🎨
Edit CSS tokens in :root for hue, radii, blur, and shadows to match your brand fast.​

Switch themes via the header toggle with user preference remembered in localStorage.

For softer or sharper glass, adjust backdrop‑filter blur or reduce effect for low‑end devices.​

Voice Features 🔊
Enable TTS with the speaker button to read the latest bot response aloud using SpeechSynthesisUtterance.​

Voice availability and quality vary by OS and browser; choose a preferred voice via getVoices when available.​

Press and hold the mic to capture a short utterance using SpeechRecognition when supported.​

Commands ⌨️
/help — Show quick usage tips and shortcuts.

/clear — Wipe the conversation in the current session.

/export — Download the chat as a JSON file.

Wire Up a Real API 🔌
Replace the mockRespond function with a fetch call to your backend that returns reply text.

Keep the typewriter effect by feeding the returned text into the existing typeStream helper.

js
// Example: replace mockRespond
async function mockRespond(q) {
  const res = await fetch('/api/chat', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ message: q })
  });
  const data = await res.json();
  return data.reply || 'No reply';
}
If using streaming backends later, progressively append chunks into typeStream for a live typing feel.

Performance Notes ⚙️
backdrop‑filter can be GPU‑intensive on some devices; reduce blur or turn off saturation for broader compatibility.​

Keep images and attachments small if you extend uploads, and consider lazy operations for previews.

Prefer efficient repaint areas and avoid large fixed blurs on mobile where possible.​

Accessibility ♿
Maintain sufficient contrast in both themes and test focus states on buttons and text areas.

Provide non‑voice fallbacks for inputs and ensure the app works fully with keyboard navigation.

Offer TTS as optional enhancement, not a requirement for content comprehension.​

Customization Tips 🧩
Swap the inline SVG icons with your own without adding any external libraries.

Tune --hue and related HSL variables to instantly shift the neon accent palette.​

Adjust border radii and shadow depth to move between “soft glass” and “sharp cyber” looks.​


