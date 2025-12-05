# AI Grid-Aware EV Fleet Orchestrator

AI Grid-Aware EV Fleet Orchestrator is a math- and AI-driven tool that schedules charging for electric vehicle (EV) fleets.  
Its goals are:
- Minimize total charging cost
- Respect site and grid power limits
- Ensure each vehicle is ready with enough energy before departure

This is an early-stage student project built by a 20-year-old BSc International Computer Science student at OTH Regensburg.  
The focus is on clear modeling, transparent assumptions, and step-by-step improvement.

---

## Problem

Companies and cities that operate EV fleets (taxis, delivery vans, buses, pool cars) face three challenges:

- Limited power at the site: they cannot charge every vehicle at full power at the same time.
- Dynamic electricity prices: some hours are expensive, some are cheap.
- Operational constraints: each vehicle must be ready (enough energy) before its next trip.

Naive charging (plug everything at once, full power) can:
- Create peak loads that stress the grid
- Increase electricity bills
- Leave some vehicles undercharged when needed

---

## Approach (v0.1)

Version 0.1 focuses on a simple, transparent optimization model:

- Time is discretized into 1-hour slots (e.g., 24 hours).
- Each vehicle has:
  - Arrival time
  - Departure time
  - Initial state of charge (SoC)
  - Required energy at departure
  - Maximum charging power
- The site has:
  - A maximum total power limit
  - A price per kWh for each time slot

The optimizer chooses how much power to give to each vehicle in each time slot, to:

- Minimize total charging cost
- Respect the site power limit at every time
- Ensure each vehicle reaches its required energy by departure

---

## Tech Stack (current)

- Language: Python
- Optimization: linear / mathematical programming (e.g., PuLP or SciPy)
- Data: simulated fleets and price profiles
- UI (planned): Streamlit-based dashboard for interactive experiments

---

## Roadmap

- **v0.1** – Core math model with simulated data
  - Generate a small fleet (10–20 vehicles)
  - Define a simple price curve
  - Implement an optimizer that returns a charging schedule
  - Print schedules and basic metrics (total cost, max power, SoC at departure)

- **v0.2** – Interactive dashboard
  - Streamlit app
  - User controls: number of vehicles, site power limit, price curve
  - Charts: power vs time, cost vs time, SoC at departure

- **v0.3** – AI-enhanced behavior
  - Simple prediction of demand or prices
  - “What-if” scenarios (e.g., more vehicles, different tariffs)

This project is work in progress and primarily educational, but aims to stay close to real-world constraints in mobility and energy.
