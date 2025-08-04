---
title: "Build Course Catalog and Student Enrollment"
labels: ["epic-2", "enrollment", "medium-priority", "must-have"]
assignees: []
milestone: "Epic 2: Course Management System"
---

## User Story
**As a student, I want to browse and enroll in courses** so that I can discover learning opportunities and access educational content.

## Description
Create a course catalog page where students can browse available courses, view course details, and enroll in courses they're interested in.

## Tasks
- [ ] Create course catalog page with course grid/list
- [ ] Implement course detail view for students
- [ ] Add enrollment functionality
- [ ] Build student dashboard showing enrolled courses
- [ ] Add course search and filtering
- [ ] Implement enrollment status tracking
- [ ] Create unenrollment functionality

## Acceptance Criteria
- [ ] Students can view all available courses
- [ ] Students can see course details (title, description, chapters)
- [ ] Students can enroll in courses with one click
- [ ] Student dashboard shows enrolled courses
- [ ] Students can search and filter courses
- [ ] Enrollment status is clearly indicated
- [ ] Students can unenroll from courses

## Technical Requirements
- Course catalog with responsive grid layout
- shadcn/ui components for UI
- Search and filter functionality
- Enrollment tracking system
- Student dashboard layout

## Database Schema
```typescript
export const enrollments = mysqlTable("enrollments", {
  id: serial("id").primaryKey(),
  studentId: varchar("student_id", { length: 255 }).notNull(),
  courseId: int("course_id").notNull(),
  enrolledAt: timestamp("enrolled_at").default(sql`CURRENT_TIMESTAMP`),
});
```

## API Endpoints
- `GET /api/courses/catalog` - List all courses for students
- `GET /api/courses/[id]/details` - Course details
- `POST /api/enrollments` - Enroll in course
- `DELETE /api/enrollments/[id]` - Unenroll from course
- `GET /api/students/enrollments` - Get student's enrolled courses

## User Interface
- Course catalog with card layout
- Course detail modal/page
- Enrollment button with status indication
- Student dashboard with enrolled courses
- Search bar and filters

## Definition of Done
- [ ] Course catalog displays correctly
- [ ] Enrollment system works properly
- [ ] Student dashboard shows relevant information
- [ ] Search and filtering function correctly
- [ ] UI is responsive and user-friendly
- [ ] Only students can enroll in courses

## Priority
**Medium** - Important for student experience

## Estimate
3 hours

## Dependencies
- Issue #4: Course Creation
- Issue #3: Role Selection
- Issue #2: User Authentication

## Related Issues
- Enables access to course content
- Required for Issue #10: AI Chat Tutor (course context)