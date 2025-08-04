---
title: "Implement Content Translation System"
labels: ["epic-3", "translation", "ai", "high-priority", "must-have"]
assignees: []
milestone: "Epic 3: AI Translation System"
---

## User Story
**As a student, I want to view course content in my language** so that I can better understand the material in my native language.

## Description
Create a comprehensive translation system that allows students to translate course chapters into their preferred language using AI, with caching for performance.

## Tasks
- [ ] Create language selection dropdown using shadcn/ui Select
- [ ] Build translation API endpoint in Python service
- [ ] Implement caching for translated content
- [ ] Connect Next.js frontend to Python translation service
- [ ] Add language preference storage
- [ ] Implement translation status indicators
- [ ] Add fallback for translation failures

## Acceptance Criteria
- [ ] Students can select their preferred language
- [ ] Chapter content translates to selected language
- [ ] Translated content is cached for performance
- [ ] Translation preserves formatting and structure
- [ ] Language preference is saved per user
- [ ] Loading states are shown during translation
- [ ] Original content is always accessible

## Technical Requirements
- Language detection and translation AI (OpenAI, Google Translate API)
- Redis or database caching
- shadcn/ui Select component
- API integration between Next.js and Python
- User preference storage

## Database Schema
```typescript
export const chapterTranslations = mysqlTable("chapter_translations", {
  id: serial("id").primaryKey(),
  chapterId: int("chapter_id").notNull(),
  language: varchar("language", { length: 10 }).notNull(),
  translatedTitle: varchar("translated_title", { length: 255 }),
  translatedContent: text("translated_content"),
  createdAt: timestamp("created_at").default(sql`CURRENT_TIMESTAMP`),
});

export const userProfiles = mysqlTable("user_profiles", {
  userId: varchar("user_id", { length: 255 }).primaryKey(),
  preferredLanguage: varchar("preferred_language", { length: 10 }),
  // ... other fields
});
```

## API Endpoints
- `POST /api/translate/chapter` - Translate chapter content
- `GET /api/translate/languages` - Get supported languages
- `PUT /api/users/language-preference` - Update user language preference

## Python Service Endpoints
- `POST /ai/translate` - AI translation service
- `GET /ai/languages` - Supported languages

## Definition of Done
- [ ] Language selection works correctly
- [ ] Translation produces accurate results
- [ ] Caching improves performance
- [ ] UI shows translation status
- [ ] User preferences are saved
- [ ] Error handling for failed translations

## Priority
**High** - Core differentiating feature

## Estimate
5-6 hours

## Dependencies
- Issue #7: Python AI Service
- Issue #5: Chapter Management
- Issue #6: Course Enrollment

## Related Issues
- Enables Issue #9: Quiz Translation
- Required for personalized learning experience