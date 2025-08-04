# GitHub Labels Configuration

This file contains the recommended labels for organizing the SEAspire project issues.

## Epic Labels
- `epic` - Large feature groups spanning multiple user stories
- Color: `#8B5CF6` (Purple)

## Priority Labels
- `high-priority` - Must-have features for MVP
- `medium-priority` - Important features for full release  
- `low-priority` - Nice-to-have features for future
- Colors: `#DC2626` (Red), `#F59E0B` (Yellow), `#10B981` (Green)

## Component Labels
- `frontend` - Next.js/React frontend work
- `backend` - API and server-side logic
- `database` - Schema and data operations
- `ai-service` - Python AI service development
- `authentication` - User auth and permissions
- `ui-ux` - User interface and experience
- Colors: `#3B82F6` (Blue), `#8B5CF6` (Purple), `#10B981` (Green), `#F59E0B` (Yellow), `#EF4444` (Red), `#EC4899` (Pink)

## Feature Labels
- `foundation` - Core platform infrastructure
- `course-management` - Course and chapter features
- `ai-translation` - Translation system
- `ai-chat` - Chat tutor features
- `quiz-system` - Assessment and grading
- `dashboard` - Analytics and tracking
- `testing` - Quality assurance
- `polish` - UI/UX improvements
- Colors: Various blues and greens

## Status Labels
- `needs-planning` - Requires detailed planning
- `needs-estimation` - Needs story point estimation
- `ready-for-dev` - Ready to start development
- `in-progress` - Currently being worked on
- `needs-review` - Awaiting code review
- `needs-testing` - Ready for QA testing
- `blocked` - Waiting on dependencies
- Colors: Various oranges and grays

## Type Labels
- `user-story` - User-focused feature story
- `task` - Technical implementation task
- `bug` - Bug fix or issue resolution
- `enhancement` - Improvement to existing feature
- `documentation` - Documentation updates
- Colors: `#0969DA` (Blue), `#1F883D` (Green), `#CF222E` (Red), `#8250DF` (Purple), `#656D76` (Gray)

## GitHub Labels JSON Configuration

```json
[
  {
    "name": "epic",
    "color": "8B5CF6",
    "description": "Large feature groups spanning multiple user stories"
  },
  {
    "name": "high-priority",
    "color": "DC2626", 
    "description": "Must-have features for MVP"
  },
  {
    "name": "medium-priority",
    "color": "F59E0B",
    "description": "Important features for full release"
  },
  {
    "name": "low-priority",
    "color": "10B981",
    "description": "Nice-to-have features for future"
  },
  {
    "name": "frontend",
    "color": "3B82F6",
    "description": "Next.js/React frontend work"
  },
  {
    "name": "backend", 
    "color": "8B5CF6",
    "description": "API and server-side logic"
  },
  {
    "name": "database",
    "color": "10B981", 
    "description": "Schema and data operations"
  },
  {
    "name": "ai-service",
    "color": "F59E0B",
    "description": "Python AI service development"
  },
  {
    "name": "authentication",
    "color": "EF4444",
    "description": "User auth and permissions"
  },
  {
    "name": "ui-ux",
    "color": "EC4899",
    "description": "User interface and experience"
  },
  {
    "name": "foundation",
    "color": "1E40AF",
    "description": "Core platform infrastructure"
  },
  {
    "name": "course-management",
    "color": "059669",
    "description": "Course and chapter features"
  },
  {
    "name": "ai-translation",
    "color": "7C3AED",
    "description": "Translation system"
  },
  {
    "name": "ai-chat",
    "color": "DB2777",
    "description": "Chat tutor features"
  },
  {
    "name": "quiz-system",
    "color": "2563EB",
    "description": "Assessment and grading"
  },
  {
    "name": "dashboard",
    "color": "0891B2",
    "description": "Analytics and tracking"
  },
  {
    "name": "testing",
    "color": "16A34A",
    "description": "Quality assurance"
  },
  {
    "name": "polish",
    "color": "C026D3",
    "description": "UI/UX improvements"
  },
  {
    "name": "user-story",
    "color": "0969DA",
    "description": "User-focused feature story"
  },
  {
    "name": "task",
    "color": "1F883D",
    "description": "Technical implementation task"
  },
  {
    "name": "needs-planning",
    "color": "D97706",
    "description": "Requires detailed planning"
  },
  {
    "name": "needs-estimation",
    "color": "B45309",
    "description": "Needs story point estimation"
  },
  {
    "name": "ready-for-dev",
    "color": "059669",
    "description": "Ready to start development"
  },
  {
    "name": "in-progress",
    "color": "0891B2", 
    "description": "Currently being worked on"
  },
  {
    "name": "needs-review",
    "color": "7C3AED",
    "description": "Awaiting code review"
  },
  {
    "name": "blocked",
    "color": "DC2626",
    "description": "Waiting on dependencies"
  }
]
```

## Label Usage Guidelines

### Labeling Epic Issues
- Always include `epic` label
- Add priority level (`high-priority`, `medium-priority`, `low-priority`)
- Add feature area label (`foundation`, `course-management`, etc.)

### Labeling User Stories
- Always include `user-story` label  
- Add priority level based on MVP requirements
- Add component labels (`frontend`, `backend`, etc.)
- Add feature area label
- Add status label as work progresses

### Labeling Tasks
- Include `task` label for technical implementation work
- Add relevant component and feature labels
- Use status labels to track progress

## Milestone Configuration

Create these milestones to organize the work:

1. **Epic 1: Core Platform Foundation** - Target: Sprint 1
2. **Epic 2: Course Management System** - Target: Sprint 2  
3. **Epic 3: AI Translation System** - Target: Sprint 3
4. **Epic 4: AI Chat Tutor** - Target: Sprint 4
5. **Epic 5: Quiz System** - Target: Sprint 4-5
6. **Epic 6: Assignment Dashboard** - Target: Sprint 6
7. **Epic 7: Testing and Polish** - Target: Sprint 7+

## Project Board Columns

Set up a GitHub project board with these columns:

1. **Backlog** - All unstarted issues
2. **Ready for Development** - Issues ready to be picked up
3. **In Progress** - Currently being worked on
4. **In Review** - Awaiting code review
5. **Testing** - Ready for QA testing  
6. **Done** - Completed and merged

This labeling system will help organize the 19 user stories across 7 epics and enable effective project management throughout development.