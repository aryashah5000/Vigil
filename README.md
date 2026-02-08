# Vigil

**Every shift change, critical knowledge walks out the door. Vigil captures it.**

---

## The Problem

Shift handoffs are where institutional knowledge dies. When your outgoing shift worker leaves, they take with them:
- Machine quirks and workarounds
- Partial fixes in progress
- Safety flags and hazard awareness
- Production bottlenecks and priorities

This costs U.S. manufacturers an estimated **$12B/year** in repeated troubleshooting, safety incidents, and lost productivity.

## The Solution

Vigil is a SaaS platform that captures and preserves shift knowledge in real-time. Workers speak naturally about their shift into a mic. Our AI processes it into structured, machine-specific handoff reports. Incoming workers get audio summaries while hands-busy on the floor. Over time, we build a persistent knowledge graph that detects cross-shift patterns and predicts maintenance needs before failures occur.

## Why Not Just ChatGPT?

ChatGPT is great for ad-hoc questions, but Vigil delivers:
- **Persistent Knowledge Graph**: Cross-shift pattern detection that improves with every handoff
- **Manufacturing Entity Recognition**: Automatic identification of machines, part numbers, and failure modes specific to your plant
- **Engagement Intelligence**: MediaPipe monitors worker alertness while reviewing briefings—ensuring critical safety information is registered
- **Predictive Signals**: Recurring patterns become actionable maintenance intelligence, turning reactive troubleshooting into proactive prevention

## Core Features

- **Hands-Free Voice Capture**: Workers record shift briefings naturally; Gemini structures it instantly
- **Smart Categorization**: Automatic severity (critical/warning/info) and type classification (safety/maintenance/quality/production)
- **Persistent Knowledge Graph**: Build institutional memory across shifts and team transitions
- **Engagement Monitoring**: MediaPipe vision-based alertness tracking during briefing review
- **Audio Summaries**: ElevenLabs generates voice summaries for busy shop floors
- **Interactive Dashboard**: Visualize all recorded briefings with machine-specific insights
- **Manufacturing Intelligence**: Recurring pattern detection for predictive maintenance
- **Fallback Resilience**: Intelligent text parsing when AI services are unavailable

## Tech Stack

### Backend
- **Framework**: FastAPI (lightweight REST API for manufacturing operations)
- **AI/ML**: Google Generative AI (Gemini 2.0 Flash) for intelligent text structuring
- **Database**: SQLite (persistent shift knowledge storage)
- **Server**: Uvicorn (production-ready ASGI server)
- **Language**: Python 3.x

### Frontend
- **Framework**: React 18 (responsive web and mobile interfaces)
- **Build Tool**: Vite (fast development and production builds)
- **Styling**: Tailwind CSS (consistent manufacturing dashboard UI)
- **Animations**: Framer Motion (smooth transitions for data visualization)
- **Vision**: MediaPipe Tasks Vision (engagement/alertness monitoring during briefing review)
- **Icons**: Lucide React (clear, accessible industrial iconography)

## Project Structure

```
vigil/
├── backend/
│   ├── main.py              # FastAPI application & core logic
│   └── requirements.txt      # Python dependencies
└── frontend/
    ├── src/
    │   ├── App.jsx          # Main application component
    │   ├── main.jsx         # React entry point
    │   ├── index.css        # Global styles
    │   └── components/      # React components
    │       ├── Dashboard.jsx
    │       ├── RecordBriefing.jsx
    │       ├── ReviewBriefing.jsx
    │       └── KnowledgeGraph.jsx
    ├── hooks/               # Custom React hooks
    │   └── useAttention.js
    ├── package.json
    ├── vite.config.js
    ├── tailwind.config.js
    └── postcss.config.js
```

 
## About

Vigil is built by an engineer who believes manufacturing deserves better tools. Every dollar saved in downtime prevention, every safety incident prevented, every worker who leaves their shift knowing the knowledge will be there for the next crew—that's what drives me.

## Team Members
Arya Shah

