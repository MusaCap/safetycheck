# 🏗️ SafeQuest MVP Sprint Plan (Bolt-Driven Execution)

## 🧱 Assumptions
- 2-week MVP timeline, 6-week full build
- AI agents handle engineering, QA, and design tickets
- Prioritized for mobile (React Native) with web dashboard for parents
- Focus: Core gameplay, onboarding, 2 safety modules, parental dashboard

---

## ⚡ Sprint 0: Project Setup & Story Decomposition (2–3 Days)

### Objectives:
- Define core components and Bolt agents needed
- Convert backlog into agent-executable tickets
- Establish architecture, stack, and APIs

### Tasks:
- [ ] Define `User`, `PlayerProfile`, `Module`, and `Progress` schemas
- [ ] Set up backend: Firebase or Supabase
- [ ] Set up React Native + Expo base project
- [ ] Create agent lanes: UX Agent, Backend Agent, Content Agent, QA Agent

---

## 🚀 Sprint 1: Onboarding Flow & User Management (Week 1)

### Goals:
- Build child/parent onboarding
- Implement parental gate (COPPA)
- Backend authentication + profile storage

### Tickets:
- [ ] Design & implement avatar-based signup for children
- [ ] Parental gate: date of birth → parental consent
- [ ] Email-based login for parents
- [ ] Backend: Auth, profile, and relational data linking
- [ ] QA tests: user flows, parental linking

**Bolt Agents Involved**: UX Agent, Backend Agent, QA Agent

---

## 🎮 Sprint 2: Core Gameplay Engine + Safety Module 1 (Week 2)

### Goals:
- Launch Stranger Danger scenario as interactive quest
- Implement core decision tree engine and visual rewards

### Tickets:
- [ ] Build `ScenarioEngine` (story tree → screens)
- [ ] Create `SafetyScore` system and badge tracking
- [ ] Design story: 3–4 decision branches, feedback
- [ ] Track per-decision data (correct, confidence, retries)
- [ ] Trigger sound/visual animations on success/failure
- [ ] UX/QA: responsive mobile UI, testable states

**Bolt Agents Involved**: Content Agent, GameLogic Agent, UX Agent

---

## 🔥 Sprint 3: Add Fire Safety Module + Gamification Layer (Week 3)

### Goals:
- Introduce second safety module
- Add reward system: badges, coins, level progress

### Tickets:
- [ ] Build Fire Safety game: fire drill sim or drag-drop escape path
- [ ] Connect mini-games to backend scoring
- [ ] Inventory + avatar customization stub (for gear/unlockables)
- [ ] Add daily streaks and safety level bar
- [ ] Agent-driven test suite for gamified logic

**Bolt Agents Involved**: GameAgent, ContentAgent, QA Agent

---

## 👨‍👩‍👧 Sprint 4: Parental Dashboard + Progress API (Week 4)

### Goals:
- Allow parents to monitor and manage content
- Integrate visual analytics of child performance

### Tickets:
- [ ] Parent web dashboard (Next.js or Expo Web)
- [ ] Visual graphs: module completion, score trends
- [ ] Module lock toggles and notifications
- [ ] Backend aggregation logic for progress and analytics
- [ ] QA test: permissions, roles, auth boundaries

**Bolt Agents Involved**: DataAgent, QA Agent, DashboardAgent

---

## 🚢 Sprint 5: Polish, Deploy, and Test Pilot Experience (Week 5–6)

### Goals:
- Smooth animations, AR hooks (stubbed), final testing
- Deploy beta via TestFlight/Play Store
- Gather feedback from 1 school and 5 families

### Tickets:
- [ ] Global styles, audio narration, accessibility pass
- [ ] Implement tutorial overlay for first-time users
- [ ] Push notification hooks (reminders, streaks)
- [ ] Export anonymized session data for pilot analytics
- [ ] Deploy to stores (agent-prepped metadata and screenshots)

**Bolt Agents Involved**: UX Agent, DeployAgent, FeedbackAgent, QA Agent

---

## ✅ Milestone Deliverables

| Sprint | Deliverable |
|--------|-------------|
| 0 | Backlog structured in Bolt, working agents |
| 1 | Onboarding & Auth, Parent/Child flows |
| 2 | Stranger Danger module + decision engine |
| 3 | Fire Safety mini-game + rewards system |
| 4 | Parental dashboard with analytics |
| 5 | Beta-ready app, accessible, feedback loops |

---

## 🎯 Success Criteria for MVP
- [ ] App launchable on iOS and Android
- [ ] 2 core safety modules completed
- [ ] COPPA-compliant and parent/child role support
- [ ] Progress data captured and visible to parents
- [ ] Game layer (score, badges, levels) functional
