# VenueFlow: Smart Stadium Operations Dashboard

VenueFlow is a React-based smart operations dashboard designed for your Google Prompt War submission. It addresses the challenges of crowd movement, waiting times, and real-time coordination by providing venue staff with real-time, simulated insights into crowd density and automated routing decisions.

## User Review Required
> [!IMPORTANT]
> Please review the proposed features and design aesthetic. Since this is a hackathon submission, we need the interface to be visually stunning. We will use a premium "dark mode" theme with glassmorphism and vibrant accent colors (neon blues and purples) to make the real-time data pop.

## Open Questions
> [!NOTE]
> 1. **Framework:** I plan to use Vite (`npx create-vite`) to bootstrap a fast, client-side React app. Does this work for you?
> 2. **Visualization:** For the stadium heatmap, I propose creating a custom, highly-polished 2D CSS/SVG grid representing different stadium zones rather than pulling in a heavy mapping library. This allows for better styling control and performance. Is this acceptable?
> 3. **Interactivity:** Should we include a "Simulation Controller" (a panel where you can manually trigger events like "Halftime Rush" or "Gate Bottleneck") to easily demonstrate the app's responsiveness to judges?

## Proposed Architecture & Features

### Setup and Infrastructure
- Bootstrap a new React application in the `promptWars` directory.
- Establish a premium Vanilla CSS design system, avoiding generic components to ensure maximum visual impact and control.

### Core Dashboard Components

#### 1. Live Stadium Heatmap
- A dynamic visual representation of the stadium divided into zones (Gates, Corridors, Concessions, Seating).
- Zones will pulse and transition colors (e.g., cool cyan for low density, warning orange/red for high density) based on a simulated real-time data feed.

#### 2. Amenities & Queue Monitor
- A dedicated metrics panel displaying real-time wait times for key amenities (Restrooms, Food Stands, Merchandise).
- Includes micro-animations when numbers update to feel truly "live."

#### 3. AI Predictive Routing & Alert Stream
- A real-time feed of simulated AI-driven actions and operational alerts.
- Example: `[AI ACTION] Rerouting Section 104 traffic to Exit C to alleviate 85% capacity bottleneck at Exit A.`
- Example: `[ALERT] Restroom South capacity exceeded; dispatching additional janitorial staff.`

#### 4. Simulation Engine (Backend Simulation)
- A React hook or context provider that runs a game-loop simulation, generating realistic fluctuations in crowd density and wait times to power the dashboard without needing a real backend.

## Verification Plan

### Automated/Local Testing
- Run the local development server and ensure the dashboard is fully responsive across standard desktop resolutions.
- Verify that the simulation loop generates smooth, realistic data fluctuations and that React efficiently re-renders the heatmap and data points without performance drops.

### Manual Verification
- Walk through a complete demonstration flow (e.g., triggering a "Rush" event) to ensure the UI updates dynamically—heatmaps turn red, AI routing alerts fire in the feed, and wait times spike and then recover, proving the solution's effectiveness for the hackathon presentation.
