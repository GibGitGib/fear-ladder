AGENT: Codex

WHAT: Build the Fear Ladder PWA engine — a self-guided exposure therapy hierarchy builder. Single HTML file. Vanilla JS, no frameworks.

CONTEXT:
- File to create: C:/Users/email/CoreTech_Sr/fear-ladder/index.html
- This is a clinically-graded exposure therapy tool. Users pick a phobia, rate feared situations 1-10 (SUDS scale), and the app builds an ascending fear ladder they climb rung by rung.
- All data stored in localStorage. No server, no account, zero dependencies.
- This is the ENGINE layer. Claude Code will handle the visual design separately (we'll merge after).
- Companion SDK is NOT needed for v1 — no AI coaching yet. Pure mechanics.

WHAT TO BUILD:

1. PHOBIA SELECTOR
- Dropdown with 25 presets: Acrophobia, Aerophobia, Claustrophobia, Agoraphobia, Arachnophobia, Ophidiophobia, Cynophobia, Trypanophobia, Astraphobia, Mysophobia, Glossophobia, Social Phobia, Thanatophobia, Nosophobia, Emetophobia, Hemophobia, Dentophobia, Vehophobia, Nyctophobia, Entomophobia, Atychiphobia, Aquaphobia, Brontophobia, Coulrophobia, Custom
- "Custom" opens a text input to type your own phobia
- Save selection to localStorage

2. SUDS RATING INTERFACE (Subjective Units of Distress Scale)
- Present 12 pre-written feared situations for the selected phobia
- Each situation has a 1-10 slider with emoji anchors (😌 calm → 😰 anxious → 😱 terrified)
- User rates each situation
- Progress bar showing X/12 completed
- Situations for acrophobia (default): "Looking at photo of tall building", "Standing on 2nd floor balcony", "Looking out 5th floor window", "Standing on 5th floor balcony with railing", "Glass elevator going up", "Rooftop with railing", "Looking over edge of 10th floor", "Standing near edge of 15th floor", "Glass floor observation deck", "Open rooftop edge, no railing", "Helicopter hovering near building", "Skydiving / bungee jumping"
- For other phobias: generate generic ladder rungs like "Thinking about [phobia]", "Looking at photo of [trigger]", "Being near [trigger]", "Touching [trigger]", etc.

3. HIERARCHY BUILDER
- Sort rated situations from lowest SUDS (easiest) to highest (hardest)
- Display as a vertical ladder (numbered rungs 1-12)
- Each rung shows: number, situation text, SUDS rating, checkbox for completion, date completed
- Color-code by difficulty: green (1-3), yellow (4-6), orange (7-8), red (9-10)

4. RUNG COMPLETION
- Click a rung to mark it "in progress" → shows a 60-second timer + "I did it" button
- User clicks "I did it" → rung marked complete, timestamp saved, next rung unlocks
- "Panic button" on active rung: immediately cancels, rung stays incomplete, no penalty
- Cannot skip rungs — must complete in order

5. STREAK SYSTEM
- Track consecutive days with at least 1 rung completed
- Display "🔥 X-day streak" in the header
- If no rung completed today, show "Start today to keep your streak!"
- localStorage keys: fearladder_streak (current count, last active date)

6. PROGRESS DASHBOARD
- "My Progress" button → modal or panel
- Shows: total rungs completed / 12, streak days, date started, last session date
- Visual: 12-dot progress bar (filled dots = completed rungs)

7. PERSISTENCE
- Save to localStorage: selected phobia, rated situations (with SUDS), completed rungs, streak data
- On reload: restore exact state
- "Reset" button in settings: clears all data after confirmation

DO NOT:
- Use React, Vue, npm, webpack, or any framework
- Use external CSS/JS dependencies
- Add AI coaching or companion SDK integration
- Style beyond basic layout (Claude Code handles design)
- Add backend/server calls

EXPECT:
- File: index.html (single file, inline CSS + JS)
- All 7 features working
- Zero console errors
- localStorage persistence survives page reload
- Mobile-responsive default layout
- ~500-800 lines total
