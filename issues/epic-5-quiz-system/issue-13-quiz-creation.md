---
title: "Create Quiz Creation System for Teachers"
labels: ["epic-5", "quiz-creation", "high-priority", "must-have"]
assignees: []
milestone: "Epic 5: Quiz System with AI Grading"
---

## User Story
**As a teacher, I want to create quizzes for my chapters** so that I can assess student understanding and provide structured learning assessments.

## Description
Build a comprehensive quiz creation system that allows teachers to create quizzes with multiple choice questions, preview functionality, and chapter integration.

## Tasks
- [ ] Build quiz creation form with dynamic question addition
- [ ] Support multiple choice questions with options
- [ ] Implement quiz preview functionality
- [ ] Add question reordering capabilities
- [ ] Create quiz validation and error handling
- [ ] Implement quiz editing and updating
- [ ] Add quiz deletion with confirmation

## Acceptance Criteria
- [ ] Teachers can create quizzes linked to chapters
- [ ] Questions can be added, edited, and removed dynamically
- [ ] Multiple choice options can be configured
- [ ] Correct answers can be designated
- [ ] Quiz preview shows student view
- [ ] Questions can be reordered
- [ ] Form validation prevents invalid quiz data

## Technical Requirements
- React Hook Form for dynamic form management
- Zod schemas for quiz validation
- shadcn/ui components for UI
- Dynamic array fields for questions
- Quiz preview functionality

## Database Schema
```typescript
export const quizzes = mysqlTable("quizzes", {
  id: serial("id").primaryKey(),
  chapterId: int("chapter_id").notNull(),
  title: varchar("title", { length: 255 }).notNull(),
  description: text("description"),
  timeLimit: int("time_limit"), // in minutes
  createdAt: timestamp("created_at").default(sql`CURRENT_TIMESTAMP`),
});

export const questions = mysqlTable("questions", {
  id: serial("id").primaryKey(),
  quizId: int("quiz_id").notNull(),
  questionText: text("question_text").notNull(),
  options: json("options").notNull(), // ["A", "B", "C", "D"]
  correctAnswer: varchar("correct_answer", { length: 10 }).notNull(), // "A"
  position: int("position"),
  points: int("points").default(1),
});
```

## API Endpoints
- `POST /api/quizzes` - Create quiz
- `GET /api/chapters/[id]/quizzes` - Get chapter quizzes
- `PUT /api/quizzes/[id]` - Update quiz
- `DELETE /api/quizzes/[id]` - Delete quiz
- `GET /api/quizzes/[id]/preview` - Preview quiz

## Quiz Creation Features
- Dynamic question addition/removal
- Multiple choice option management
- Correct answer selection
- Question reordering
- Quiz metadata (title, description, time limit)
- Preview mode
- Save as draft functionality

## Definition of Done
- [ ] Quiz creation form works correctly
- [ ] Questions can be added and managed
- [ ] Quiz preview functions properly
- [ ] Data validation prevents errors
- [ ] Only chapter owners can create quizzes
- [ ] UI is intuitive and responsive

## Priority
**High** - Essential for assessment functionality

## Estimate
4-5 hours

## Dependencies
- Issue #5: Chapter Management
- Issue #4: Course Creation
- Issue #1: Project Foundation

## Related Issues
- Enables Issue #14: Quiz Taking
- Required for Issue #15: AI Grading