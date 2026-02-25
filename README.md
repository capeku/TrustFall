# TrustFall

An interactive Prisoner's Dilemma game built with Nuxt.js. Make strategic decisions against an adaptive AI opponent across 5 rounds, with outcomes influenced by dice rolls and accumulated consequences.

## Features

- **Strategic Gameplay**: Choose to Cooperate, Negotiate, or Betray each round
- **Adaptive AI**: Opponent learns from your historical play patterns across games
- **Dice Mechanics**: D12 rolls modify outcomes with critical successes and failures
- **Consequence System**: Your actions carry weight into future rounds
- **Dynamic Narratives**: AI-generated story elements that respond to your choices
- **3D Dice Rolling**: Physics-based dice visualization
- **PWA Support**: Install on mobile devices for offline play

## Tech Stack

- **Framework**: Nuxt.js 3 / Vue 3
- **Backend**: Firebase (Authentication + Realtime Database)
- **3D Graphics**: Three.js + Cannon-es (physics)
- **AI Narrative**: OpenAI
- **State Management**: Pinia
- **Styling**: TailwindCSS + Flowbite
- **Animations**: Lottie

## Getting Started

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Project Structure

```
TrustFall/
├── components/          # Vue components
│   ├── GamePlay.vue     # Main game interface
│   ├── DiceRoller.client.vue  # 3D dice component
│   ├── GameSummary.vue  # End-game results
│   └── ...
├── composables/         # Game logic
│   ├── useGame.js       # Core game state & mechanics
│   ├── useAIDialogue.js # AI narrative generation
│   ├── useSceneManager.js # Scene/scenario management
│   ├── useDiceRoll.js   # Dice rolling logic
│   └── ...
├── pages/               # App routes
│   ├── index.vue        # Login/signup
│   ├── GameMenu.vue     # Game selection
│   ├── game/[id].vue    # Active game
│   └── ...
├── stores/              # Pinia state stores
└── assets/              # Images, animations, styles
```

## Game Mechanics

### Choices & Outcomes

| Your Choice | AI Cooperates | AI Negotiates | AI Betrays |
|-------------|---------------|---------------|------------|
| Cooperate   | 3 / 3         | 2 / 3         | 0 / 5      |
| Negotiate   | 3 / 2         | 4 / 4         | 1 / 4      |
| Betray      | 5 / 0         | 4 / 1         | 1 / 1      |

*Format: Your Points / AI Points*

### Dice Modifiers

- **Critical Success (12)**: +25% point multiplier
- **Critical Failure (2)**: -25% point multiplier
- **Beat DC**: +10% bonus
- **Miss DC**: -10% penalty

### Consequences

Actions generate consequences that persist across rounds:
- **Loyalty**: +2 to cooperation rolls
- **Deception**: +1 to betrayal attempts
- **Critical Success/Failure**: Lasting roll modifiers

## License

MIT
