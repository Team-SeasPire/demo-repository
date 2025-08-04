---
title: "Build Quiz Taking Interface for Students"
labels: ["epic-5", "quiz-taking", "high-priority", "must-have"]
assignees: []
milestone: "Epic 5: Quiz System with AI Grading"
---

## User Story
**As a student, I want to take quizzes** so that I can test my understanding of the course material and track my learning progress.

## Description
Create an intuitive quiz-taking interface that allows students to complete quizzes with proper form handling, progress tracking, and timer functionality.

## Tasks
- [ ] Create quiz-taking interface using React Hook Form
- [ ] Implement submission and progress tracking
- [ ] Add quiz timer functionality
- [ ] Create question navigation (previous/next)
- [ ] Add answer selection and validation
- [ ] Implement auto-save functionality
- [ ] Create quiz completion confirmation

## Acceptance Criteria
- [ ] Students can access quizzes from enrolled courses
- [ ] Quiz interface shows questions clearly
- [ ] Students can select answers and navigate questions
- [ ] Timer counts down and auto-submits when expired
- [ ] Progress indicator shows completion status
- [ ] Students can review answers before submission
- [ ] Quiz submits successfully with all answers

## Technical Requirements
- React Hook Form for form management
- Timer implementation with auto-submit
- Local storage for auto-save
- Progress tracking UI
- Answer validation
- Quiz navigation controls

## Database Schema
```typescript
export const submissions = mysqlTable("submissions", {
  id: serial("id").primaryKey(),
  quizId: int("quiz_id").notNull(),
  studentId: varchar("student_id", { length: 255 }).notNull(),
  answers: json("answers").notNull(), // {"1": "A", "2": "B", ...}
  score: int("score"),
  feedback: text("feedback"),
  startedAt: timestamp("started_at").default(sql`CURRENT_TIMESTAMP`),
  submittedAt: timestamp("submitted_at"),
  timeSpent: int("time_spent"), // in seconds
});
```

## API Endpoints
- `GET /api/quizzes/[id]/take` - Get quiz for taking
- `POST /api/quiz-attempts` - Start quiz attempt
- `PUT /api/quiz-attempts/[id]/save` - Auto-save progress
- `POST /api/quiz-attempts/[id]/submit` - Submit quiz

## Quiz Taking Features
- Clean, distraction-free interface
- Question counter (e.g., "Question 3 of 10")
- Timer with visual countdown
- Previous/Next navigation
- Answer selection with clear feedback
- Review page before submission
- Auto-save every 30 seconds
- Submit confirmation

## User Interface
- Single question per page layout
- Clear question text and options
- Radio buttons for multiple choice
- Progress bar at top
- Timer in prominent position
- Navigation buttons
- Submit button with confirmation

## Definition of Done
- [ ] Quiz interface loads correctly
- [ ] Students can answer questions and navigate
- [ ] Timer works and auto-submits
- [ ] Answers are saved properly
- [ ] Submission process completes successfully
- [ ] UI is accessible and user-friendly

## Priority
**High** - Core assessment functionality

## Estimate
3-4 hours

## Dependencies
- Issue #13: Quiz Creation
- Issue #6: Course Enrollment
- Issue #2: User Authentication

## Related Issues
- Enables Issue #15: AI Grading
- Required for Issue #16: Assignment Tracking