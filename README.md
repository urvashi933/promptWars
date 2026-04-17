# promptWars
Submission for Google Prompt War: Physical Event Experience. VenueFlow is a React-based smart dashboard that leverages simulated real-time sensor data and predictive AI to route attendees efficiently and reduce queue times.
This README is structured to highlight both your technical implementation and your strategic thinking, specifically mapping your features to the competition’s judging criteria.

## 🏟️ VenueFlow: Smart Stadium Operations Dashboard
**VenueFlow** is a real-time, AI-driven command center designed for stadium operations managers to monitor crowd density, optimize staff allocation, and mitigate bottlenecks dynamically.
## 🎯 Chosen Vertical
**Operational Efficiency & Crowd Management**
- **Persona**: Stadium Operations Director / Safety Lead.
- **Problem**: Large-scale venues often suffer from "blind spots" where congestion at one gate or concession stand leads to safety risks and lost revenue.
- **Solution**: A dynamic assistant that interprets telemetry data to provide actionable rerouting and pricing recommendations.

## 💡 Approach and Logic
The project follows a "**Observe → Interpret → Act**" logic flow:
1. **Observe (Telemetry)**: The system simulates high-volume data streams (attendee counts, queue wait times, and zone occupancy) using a custom React simulation engine.
2. **InterpretContextual Logic)**:
   - **Bottleneck Detection**: If a Gate's occupancy ratio exceeds $0.8$ ($80\%$), the system identifies a bottleneck.
   - **Flow Analysis**: The assistant compares wait times across different sectors to find underutilized "overflow" areas.
3. **Act (Dynamic Assistance)**:
   - **Visual Routing**: The UI renders animated SVG "Flow Arrows" to guide staff on where to divert attendees.
   - **Economic Incentives**: The "Surge Pricing" module automatically triggers discounts at under-capacity concession stands to pull crowds away from congested areas.
     
## 🛠️ How the Solution Works
**Technical Stack**
- **Frontend**: React.js (Hooks-heavy architecture for state management).
- **Animations**: GSAP for UI transitions and SVG path manipulation for the "Flow" arrows.
- **Real-Time Simulation**: A custom engine using setInterval and requestAnimationFrame to mimic fluctuating crowd data.
- **Accessibility**: Web Audio API integration provides auditory alerts for critical system changes, ensuring the "assistant" is effective even when the user is multitasking.

**Key Features**
- **Interactive Heatmap**: A live SVG map that shifts colors based on real-time capacity ratios _(Load/Capacity)_.
- **Sticky Telemetry Bar**: High-level stats (Total Attendees, Status) remain fixed at the top for constant situational awareness.
- **AI Coordination Panel**: A dedicated feed for system-generated alerts that translate raw data into plain-English instructions.
- **Micro-Scroll Wait Times**: A constrained, scrollable list of checkpoints that highlights "Critical" (Red) vs "Good" (Green) wait times.
  
## 🚀 Deployment (Google Cloud)
The project is built and deployed using the latest Google Cloud ecosystem:
- **Google Antigravity**: Used for agent-driven project transformation and deployment workflows.
- **Google App Hosting / Cloud Run**: The solution is hosted on a serverless Cloud Run instance, providing a publicly accessible and scalable URL.

## 📋 Assumptions Made
1. **Data Ingestion**: It is assumed that the stadium is equipped with IoT sensors (optical counters or RFID) that provide a JSON stream of occupancy counts every 3 seconds.
2. **User Access**: The dashboard is designed for desktop/tablet use in a central control room environment.
3. **Connectivity**: The system assumes a persistent internet connection to sync AI recommendations from the cloud-hosted logic to the local UI.
4. **Staff Mobility**: Alerts generated (e.g., "Diverting flow to Gate 2") assume that ground staff are equipped with mobile devices to receive and execute these digital commands.
  
## Maintainability
The codebase follows a modular structure:
- useSimulation.js: Isolates the data logic from the UI.
- useAudioEngine.js: Manages audio feedback separately.
- _CSS Variables_: All status colors and theme elements are controlled via :root variables for rapid re-branding.
