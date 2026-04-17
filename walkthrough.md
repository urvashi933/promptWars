# VenueFlow: Project Walkthrough

The development of the **VenueFlow** smart stadium dashboard for your Google Prompt War submission is complete! 

I have built the application using a single-page approach. Because Node.js was not available in your environment to run standard build tools like Vite, I designed the application to run natively in any modern web browser using **React and Babel via CDNs**. This is perfect for a hackathon environment as it requires zero setup—you simply open the file.

## What Was Built

### 1. The Core Application (`index.html` & `app.jsx`)
The dashboard is a fully functional React application. It uses React 18, utilizing `useState`, `useEffect`, `useMemo`, and `useCallback` hooks to manage state and power the live simulation. 

- **Live Simulation Engine**: A custom `useSimulation` hook powers the entire dashboard. It generates realistic, fluctuating data for crowd density across 5 zones and wait times for 4 amenities, simulating the dynamic nature of a physical event.
- **Heatmap (`Heatmap` component)**: A 2D SVG representation of the stadium. Zones dynamically change color (Green -> Yellow -> Red) and pulse when they reach critical capacity.
- **Queue Monitor (`QueueMonitor` component)**: Displays real-time wait times and trend indicators (Increasing/Decreasing/Stable).
- **Alert Stream (`AlertStream` component)**: An AI routing feed that simulates automated actions, like rerouting traffic away from congested gates.

### 2. Premium Design System (`styles.css`)
I implemented a highly aesthetic, bespoke design system using pure CSS.
- **Dark Mode & Glassmorphism**: The UI utilizes a dark space-blue background with translucent, blurred panels (`backdrop-filter: blur()`) to create a stunning, high-tech command center feel.
- **Micro-animations**: Hover states, smooth color transitions on the heatmap, and alert slide-in animations make the dashboard feel alive and responsive.
- **Typography & Icons**: We utilized Google Fonts (Outfit & Inter) and Phosphor Icons to ensure the UI looks polished and professional.

## How to Test and Present

Since this is a client-side application, running it is incredibly simple:

> [!TIP]
> 1. Open your File Explorer and navigate to `c:\Users\Lenovo\Desktop\promptWars`.
> 2. Double-click on `index.html`. It will open in your default web browser.

**Demonstration Script for Judges:**
1. Show them the **Baseline Flow**, explaining how the Heatmap and Wait Times update dynamically based on the live sensors.
2. Click **"Simulate Halftime Rush"** in the Simulation Controller panel. Point out how wait times spike, trends change to "Increasing", and the concourse turns red.
3. Click **"Simulate Gate A Bottleneck"**. Show how the Heatmap for Gate A pulses red and watch the AI Alert Stream generate an automated routing message to alleviate the crowd.

Good luck with your Prompt War submission! The visual polish and real-time React simulation should make for an incredibly strong presentation.
