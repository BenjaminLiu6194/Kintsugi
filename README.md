# Kintsugi

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

## Getting Started

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build
```

