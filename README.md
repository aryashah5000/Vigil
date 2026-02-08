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

### Ready for Integration
- **ElevenLabs Audio**: For voice summary generation (coming soon)
- **Manufacturing NER**: Pipeline-ready for entity extraction (machines, parts, failure modes)

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

## Getting Started

### Prerequisites
- Python 3.8+
- Node.js 16+
- Google Generative AI API key

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install Python dependencies:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file with your API key:
```
GEMINI_API_KEY=your_api_key_here
```

4. Run the FastAPI server:
```bash
uvicorn main:app --reload
```

The backend will be available at `http://localhost:8000`

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Build for production:
```bash
npm run build
```

The frontend will be available at `http://localhost:5173`

## API Endpoints

### Briefings
- `GET /api/briefings` - Retrieve all briefings
- `POST /api/briefings` - Create a new briefing from raw text
- `GET /api/briefings/{id}` - Get a specific briefing
- `DELETE /api/briefings/{id}` - Delete a briefing

### Attention Logs
- `POST /api/attention-logs` - Log attention/focus data
- `GET /api/attention-logs` - Retrieve attention logs

## How It Works

### The Handoff Loop

1. **Outgoing Shift Capture** (5 minutes): Workers speak naturally about their shift—machine issues, workarounds, safety flags, priorities
2. **AI Structuring** (seconds): Gemini processes audio/text into structured machine-specific items with severity and category
3. **Knowledge Persistence**: The briefing and its patterns are stored in the persistent knowledge graph
4. **Incoming Worker Review** (3 minutes): Incoming crew reviews the handoff (text + audio summary)
5. **Engagement Monitoring**: MediaPipe monitors alertness during review—critical safety items demand attention
6. **Pattern Recognition**: Over time, recurring machine issues become predictive maintenance signals

### The Competitive Edge

- **Knowledge Stays With the Plant**: Unlike ChatGPT conversations that disappear, every shift adds to institutional memory
- **Manufacturing-Aware**: Learns your machines, your failure modes, your part taxonomy
- **Proactive, Not Reactive**: Patterns become predictive—fix the machine before it breaks, not after
- **Accountability**: Digital trail of what was communicated at handoff—invaluable for safety audits and training

## Data Structure

Each briefing preserves shift intelligence with:

```json
{
  "id": "briefing_id",
  "shift": "A",
  "timestamp": "2026-02-08T06:00:00Z",
  "author": "shift_supervisor_name",
  "summary": "Shift briefing with critical safety alert on Press-3 and pending maintenance for AutoLoader-1",
  "items": [
    {
      "id": 1,
      "machine_id": "Press-3",
      "category": "safety",
      "severity": "critical",
      "title": "Emergency stop button sticking",
      "details": "E-stop on Press-3 requires harder push than normal",
      "action_required": "Replace E-stop assembly before production resumes"
    }
  ],
  "recurring_patterns": ["Press-3 hydraulic pressure spikes", "AutoLoader-1 part jams"],
  "machines_mentioned": ["Press-3", "AutoLoader-1", "Conveyor-B"],
  "maintenance_signals": ["Press-3 requires preventive hydraulic service"]
}
```

This structure enables:
- **Machine-specific dashboards**: See all issues for that machine over time
- **Cross-shift pattern detection**: "Press-3 had 5 E-stop issues in 3 weeks—schedule rebuild"
- **Predictive maintenance**: Recurring patterns become work orders before failures
- **Safety compliance**: Digital trail of all safety-critical communications

---

## Target Market

**Manufacturing Plants** (specifically):
- Automotive suppliers and OEMs
- Food & beverage production
- Pharmaceutical manufacturing
- Discrete manufacturing (heavy equipment, appliances, etc.)

**Personas**:
- _Plant Managers_: Eliminate knowledge loss, reduce downtime, improve safety metrics
- _Shift Supervisors_: Standardize handoffs, ensure critical info gets communicated
- _Maintenance Teams_: Predictive signals instead of reactive troubleshooting
- _Operations Teams_: Digital audit trail and compliance reporting

**The Value Proposition**:
- Recover $50K-$200K/year per plant in reduced downtime
- Improve safety compliance and incident prevention
- Build institutional memory across team turnover
- Reduce overtime spent troubleshooting recurring issues

---

## Roadmap

- [ ] **MVP**: Core briefing capture, structuring, and dashboard
- [ ] **ElevenLabs Integration**: Voice summaries for incoming shifts
- [ ] **Advanced MediaPipe Engagement**: Alert notifications when worker attention drops during critical items
- [ ] **Manufacturing NER Pipeline**: Industry-specific entity recognition (machine IDs, part numbers, failure codes)
- [ ] **Predictive Maintenance Dashboard**: Pattern analysis and work order generation
- [ ] **Multi-Plant Analytics**: Cross-facility benchmarking and trend analysis
- [ ] **Mobile App**: Native iOS/Android for shop floor access
- [ ] **Integrations**: Maintenance systems (SAP, Oracle), PLCs, IoT sensors

---

## Contributing

We're building Vigil with manufacturing partners. If you're interested in:
- **Beta testing** at your facility
- **Contributing features** or integration ideas
- **Providing feedback** on the platform

Please reach out: [contact info coming soon]

## License

Vigil source code is provided under the MIT License. See LICENSE file for details.

## About

Vigil is built by engineers who believe manufacturing deserves better tools. Every dollar saved in downtime prevention, every safety incident prevented, every worker who leaves their shift knowing the knowledge will be there for the next crew—that's what drives us.

**Questions?** Open an issue or reach out to our team.

