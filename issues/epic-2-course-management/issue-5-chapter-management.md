---
title: "Implement Chapter Management for Courses"
labels: ["epic-2", "chapters", "high-priority", "must-have"]
assignees: []
milestone: "Epic 2: Course Management System"
---

## User Story
**As a teacher, I want to add chapters to my courses** so that I can structure my content in an organized, logical sequence for students.

## Description
Create a chapter management interface that allows teachers to add, edit, reorder, and manage rich content within their courses.

## Tasks
- [ ] Create chapter management interface
- [ ] Implement rich text editor for chapter content
- [ ] Add chapter ordering/positioning functionality
- [ ] Create chapter CRUD operations
- [ ] Implement drag-and-drop reordering
- [ ] Add chapter preview functionality
- [ ] Create chapter validation

## Acceptance Criteria
- [ ] Teachers can add new chapters to their courses
- [ ] Teachers can edit existing chapter content
- [ ] Teachers can reorder chapters within a course
- [ ] Rich text editor supports formatting (bold, italic, lists, etc.)
- [ ] Chapter position is maintained correctly
- [ ] Teachers can preview chapters as students would see them
- [ ] Chapter content is properly validated

## Technical Requirements
- Rich text editor (TinyMCE, Quill, or Tiptap)
- Drag-and-drop library (dnd-kit)
- React Hook Form for chapter forms
- Zod validation schemas
- Position management logic

## Database Schema
```typescript
export const chapters = mysqlTable("chapters", {
  id: serial("id").primaryKey(),
  courseId: int("course_id").notNull(),
  title: varchar("title", { length: 255 }).notNull(),
  content: text("content"),
  position: int("position"),
  createdAt: timestamp("created_at").default(sql`CURRENT_TIMESTAMP`),
});
```

## API Endpoints
- `POST /api/courses/[courseId]/chapters` - Create chapter
- `GET /api/courses/[courseId]/chapters` - List chapters
- `PUT /api/chapters/[id]` - Update chapter
- `DELETE /api/chapters/[id]` - Delete chapter
- `PUT /api/chapters/reorder` - Reorder chapters

## Definition of Done
- [ ] Chapter CRUD operations work correctly
- [ ] Rich text editor functions properly
- [ ] Chapter ordering system works
- [ ] Content is properly saved and displayed
- [ ] Only course owners can manage chapters
- [ ] UI is intuitive and responsive

## Priority
**High** - Essential for content creation

## Estimate
3-4 hours

## Dependencies
- Issue #4: Course Creation
- Issue #1: Project Foundation

## Related Issues
- Enables Issue #8: Content Translation
- Required for Issue #13: Quiz Creation