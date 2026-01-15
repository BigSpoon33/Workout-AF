# Workout AF

A workout planning and exercise tracking system for Obsidian, built with DatacoreJSX components.

## Features

- **Exercise Library** - Store exercises with form cues, variations, and progress tracking
- **Workout Builder** - Create custom workout plans from your exercise library
- **Weekly Planner** - Schedule workout plans across your week
- **Muscle Map** - Visual anatomy reference showing target muscles
- **Mobile-Friendly** - Touch-optimized components for gym use

## Workflow

### 1. Add Exercises

**Option A: Web Clipper**
Use the Obsidian Web Clipper to save exercises from fitness sites. The clipper captures exercise details automatically.

**Option B: Manual Entry**
Create a new note using the Exercise Template (`System/Templates/Exercise Template.md`).

**Exercise Frontmatter:**
```yaml
categories:
  - "[[Exercise]]"
type: [strength, compound]
target: [chest, triceps, shoulders]
equipment: [barbell, bench]
duration:
sets: 4
reps: 8
weight: 135
rating: 5
created: 2026-01-14
last:
```

### 2. Build Workout Plans

Create workout plans by combining exercises:

1. Create a new note from the Workout-Plan Template
2. Add exercises to your plan
3. Set target sets, reps, and rest periods
4. Use the **Workout Builder** widget to organize exercises

### 3. Schedule Your Week

Open the **Exercise Planner** (`System/Planners/Exercise Planner.md`):

- Assign workout plans to each day of the week
- View your weekly training schedule at a glance
- Frontmatter stores your schedule:

```yaml
schedule-monday: "[[Push Day]]"
schedule-tuesday: "[[Legs]]"
schedule-wednesday:
schedule-thursday: "[[Pull Day]]"
schedule-friday: "[[Push Day]]"
schedule-saturday: "[[Legs]]"
schedule-sunday:
```

### 4. Track Progress

Each exercise note tracks:
- **Last performed** - When you last did this exercise
- **Weight** - Current working weight
- **Sets/Reps** - Your current programming
- **Notes** - Personal observations and modifications

## Folder Structure

```
Workout AF/
├── System/
│   ├── Assets/
│   │   └── Anatomy/     # Muscle map SVGs and data
│   ├── Categories/      # Exercise, Workout Plan
│   ├── Dashboards/      # Component showcase
│   ├── Planners/        # Weekly Exercise Planner
│   ├── Scripts/
│   │   ├── Components/  # UI components
│   │   ├── Core/        # Theme and utilities
│   │   └── Widgets/     # Workout-specific widgets
│   │       ├── dc-muscleMap.jsx
│   │       ├── dc-weeklyWorkout.jsx
│   │       ├── dc-workoutBuilder.jsx
│   │       └── dc-workoutToday.jsx
│   ├── Templates/
│   │   ├── Bases/       # Obsidian Bases views
│   │   ├── Exercise Template.md
│   │   └── Workout-Plan Template.md
│   ├── Themes/          # UI themes
│   ├── Workout Plans/   # Saved workout plans
│   └── Settings.md
├── Examples/            # Example exercises
└── README.md
```

## Requirements

- Obsidian v1.0+
- Datacore plugin
- Minimal Theme by Kepano (recommended)
- Style Settings plugin (for theme customization)

## Quick Start

1. Install required plugins (see INSTALLATION.md)
2. Create exercises using the Exercise Template
3. Build workout plans from your exercise library
4. Schedule your week with the Exercise Planner
5. Hit the gym!

## Credits

Part of the AF Vault Capsule series by Rice AF.

---

<a href='https://ko-fi.com/M4M11S2NNW' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://storage.ko-fi.com/cdn/kofi6.png?v=6' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>
