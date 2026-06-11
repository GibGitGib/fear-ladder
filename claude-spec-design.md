AGENT: Claude Code (Designer)

WHAT: Design the Fear Ladder PWA — a calm, clinical, trustworthy UI for a self-guided exposure therapy app.

CONTEXT:
- File to style: C:/Users/email/CoreTech_Sr/fear-ladder/index.html
- Codex is simultaneously building the engine (phobia selector, SUDS sliders, hierarchy builder, streak system). You design the visual layer.
- Target: people with anxiety/phobias. The UI must feel SAFE, calm, and professional — NOT gamified or playful.
- Single HTML file. Add your CSS inside the same file. No external fonts or dependencies.
- Mobile-first PWA. Must work on phones (primary device).
- This is clinical-adjacent. Think "therapy app" not "game." Trust is everything.

DESIGN DIRECTION:
- **Palette:** Soft blues (#E8F0FE, #B3D4FF) and warm neutrals (#F5F0EB, #D4C5B9). Accent: sage green (#7EB8A2) for completion/progress. Warning/panic: soft coral (#E8927C) — never pure red.
- **Typography:** System font stack, generous line-height (1.6+), large touch targets (44px+)
- **Tone:** Clean, airy, lots of whitespace. Think Headspace meets a medical app. Cards with soft rounded corners (16px+), subtle shadows.
- **No dark patterns.** No urgency, no scarcity, no "limited time" anything. This is for anxious people.
- **Panic button:** Always visible, clearly labeled "I need a break" with a gentle icon. Must be easy to find, impossible to accidentally trigger.

WHAT TO STYLE:

1. APP SHELL
- Centered max-width container (440px on desktop, full-width on mobile)
- Soft gradient background (light blue → warm white)
- App logo/header: "Fear Ladder" with a subtle ladder icon or just clean typography
- Streak badge (🔥 X days) in header, small and encouraging

2. PHOBIA SELECTOR
- Large, friendly dropdown with emoji prefix per phobia (🏢 Acrophobia, ✈️ Aerophobia, etc.)
- Custom input slides in smoothly when "Custom" selected
- Selected state: soft blue highlight, checkmark

3. SUDS SLIDER CARDS
- Each feared situation on its own card
- Slider with 1-10 scale, emoji anchors at ends (😌 → 😱)
- Current rating displayed prominently above slider
- Progress indicator: "5 of 12 rated"
- Cards animate in one at a time with subtle fade-up

4. FEAR LADDER (HIERARCHY VIEW)
- Vertical ladder — each rung is a card
- Color-coded left border (green 1-3, yellow 4-6, orange 7-8, red 9-10)
- Completed rungs: faded slightly, green checkmark, date stamp
- Current rung: subtle glow/pulse
- Locked rungs: muted, lock icon
- "Start" button on the next unlocked rung

5. ACTIVE SESSION
- Full-screen modal when user clicks "Start" on a rung
- 60-second countdown timer, large and centered
- Situation text displayed prominently: "Standing on a 5th floor balcony"
- Two buttons: "I did it ✅" (completion) and "I need a break 🧘" (panic)
- "I need a break" → smooth transition to grounding screen

6. GROUNDING SCREEN (post-panic or post-session)
- Calm screen: "You did great. Take a breath."
- Simple breathing animation (circle expanding/contracting, 4-7-8 pattern)
- "Continue" button to return to ladder

7. PROGRESS DASHBOARD
- Slide-in panel from right
- Stats: "8 of 12 rungs completed", "🔥 5-day streak", "Started June 6"
- Visual: horizontal dots (12 circles, filled = completed)
- "Reset progress" link at bottom (with confirmation)

8. PRO UPSELL (subtle)
- After completing 3 rungs: gentle nudge — "Unlock unlimited phobias and AI coaching"
- Not a popup. A soft banner at the bottom of the ladder.
- Link to Gumroad (placeholder for now)
- Never blocks the user. Always dismissible.

DESIGN PRINCIPLES:
- Every interaction should feel deliberate, never rushed
- Animations: slow (300-400ms), ease-out, never jarring
- No auto-advancing anything without user tap
- Panic button is a right, not a failure
- Language: "You" not "the user." "Take your time" not "Complete all steps."

DO NOT:
- Modify any JavaScript/engine code (Codex owns that)
- Add external fonts, icons, or CSS frameworks
- Use pure red (#FF0000) anywhere — even for panic button
- Add aggressive animations, popups, modals that block dismissal
- Style anything as "urgent" or "limited"

EXPECT:
- File: index.html (add your CSS inside <style> tags, don't touch Codex's JS)
- All 8 sections styled
- Mobile-first, responsive
- Zero visual jarring
- Feels like a therapist's office, not a startup's landing page
