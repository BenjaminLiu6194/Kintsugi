# Nemo - Mood-Reactive Journal

A modern journaling app that adapts its UI based on the emotional tone of your entries.

### 1. Mood Detection
- **Stub Implementation**: Keyword-based analysis in `src/lib/moodAnalyzer.js`
- Detects moods: calm, nostalgic, energetic, melancholic, chaotic, neutral
- Returns sentiment (positive/negative/neutral) and confidence score
- **TODO**: Replace with LLM API (OpenAI, Anthropic, etc.)

### 2. Dynamic Theming
Six mood themes in `src/theme/moodThemes.js`:
- **Calm** - Soft blues, slow animations
- **Nostalgic** - Warm sepia tones
- **Energetic** - Vibrant colors, fast animations
- **Melancholic** - Deep blues/grays, minimal movement
- **Chaotic** - High contrast, erratic animations
- **Neutral** - Grayscale, subtle effects

Each theme defines:
- Color palette (primary, secondary, accent, etc.)
- Animation properties (speed, intensity, type)
- Gradient backgrounds

### 3. Reactive UI
- Background animations change based on detected mood
- Color scheme adapts in real-time while typing
- Smooth transitions between moods using Framer Motion
- Particle effects with varying intensity

### 4. Components

#### `<JournalEntry />`
- Real-time mood preview while typing
- Auto-saves with mood analysis
- Visual feedback showing detected mood
- Character counter

#### `<MoodReactiveBackground />`
- Animated gradient backgrounds
- Floating particles (count/speed based on mood intensity)
- Ambient light effects
- Smooth theme transitions

#### `<EntryList />`
- Card-based grid layout
- Color-coded by mood
- Staggered animations on load
- Responsive design

#### `<Navbar />`
- Current mood indicator
- Quick "New Entry" button
- Animated logo with theme color

### 5. Routing
- `/` - Home page with entry list
- `/entry/new` - Create new entry
- `/entry/:id` - View/edit existing entry

### 6. State Management
Context-based (`JournalContext`) provides:
- `entries` - All journal entries
- `currentTheme` - Active mood theme
- `createEntry()` - Add new entry
- `updateEntry()` - Modify existing entry
- `deleteEntry()` - Remove entry
- `previewMood()` - Real-time mood detection

Data persists to localStorage.

## Getting Started

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build
```

## Sample Entries

Two example entries are pre-loaded:
1. Nostalgic entry about beach memories
2. Calm entry about meditation

## Next Steps

### High Priority
- [ ] Replace mood analyzer with LLM API
- [ ] Add user authentication
- [ ] Cloud storage/sync

### Enhancements
- [ ] Export entries (PDF, Markdown)
- [ ] Mood calendar/analytics
- [ ] Search and filters
- [ ] Rich text editor
- [ ] Image attachments
- [ ] Three.js 3D backgrounds (optional)

### UX Improvements
- [ ] Dark mode toggle
- [ ] Custom theme editor
- [ ] Keyboard shortcuts
- [ ] Mobile app (React Native)

## Architecture Notes

### Why This Structure?
- **Modular components**: Easy to replace/extend
- **Theme engine separation**: Simple to add new moods
- **Stub analyzer**: Drop-in replacement for LLM later
- **Context over Redux**: Simpler for this scope
- **shadcn-style components**: Customizable, accessible

### Performance
- Debounced mood preview during typing
- Lazy loading for entries list
- CSS transforms for animations (GPU-accelerated)
- LocalStorage for instant load

### Extensibility
The theme engine and mood analyzer are designed as independent modules:
- Add new moods by extending `moodThemes.js`
- Swap analyzer by implementing same interface in `moodAnalyzer.js`
- Components consume themes generically via context

## License

MIT
