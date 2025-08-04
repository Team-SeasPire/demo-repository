---
title: "Extend Translation System to Quiz Questions"
labels: ["epic-3", "quiz-translation", "ai", "medium-priority", "nice-to-have"]
assignees: []
milestone: "Epic 3: AI Translation System"
---

## User Story
**As a student, I want to see quiz questions in my language** so that I can fully understand what is being asked and demonstrate my knowledge effectively.

## Description
Extend the existing translation system to handle quiz questions and multiple choice options, ensuring the entire quiz experience is localized for students.

## Tasks
- [ ] Extend translation system to quiz questions
- [ ] Handle translation of multiple choice options
- [ ] Implement quiz translation caching
- [ ] Add translation for quiz instructions
- [ ] Ensure answer validation works with translations
- [ ] Add language consistency across quiz elements

## Acceptance Criteria
- [ ] Quiz questions translate to student's language
- [ ] Multiple choice options are translated correctly
- [ ] Quiz instructions and labels are localized
- [ ] Answer validation works regardless of language
- [ ] Entire quiz experience is in selected language
- [ ] Translation maintains question meaning and difficulty
- [ ] Performance is optimized with caching

## Technical Requirements
- Extension of existing translation API
- Quiz translation caching strategy
- Validation logic that handles translations
- Consistent language experience

## Database Schema Extensions
```typescript
export const questionTranslations = mysqlTable("question_translations", {
  id: serial("id").primaryKey(),
  questionId: int("question_id").notNull(),
  language: varchar("language", { length: 10 }).notNull(),
  translatedQuestionText: text("translated_question_text"),
  translatedOptions: json("translated_options").notNull(),
  createdAt: timestamp("created_at").default(sql`CURRENT_TIMESTAMP`),
});
```

## API Endpoints
- `POST /api/translate/quiz` - Translate entire quiz
- `POST /api/translate/question` - Translate single question
- `GET /api/quiz/[id]/translated/[language]` - Get translated quiz

## Python Service Extensions
- `POST /ai/translate/quiz` - AI quiz translation
- `POST /ai/translate/question` - AI question translation

## Special Considerations
- Preserve question difficulty level
- Maintain answer correctness
- Handle technical terms appropriately
- Consider cultural context in translations

## Definition of Done
- [ ] Quiz questions translate correctly
- [ ] Multiple choice options maintain meaning
- [ ] Answer validation works with translations
- [ ] Performance is acceptable with caching
- [ ] UI shows quiz in consistent language
- [ ] Translation quality is maintained

## Priority
**Medium** - Enhances the localization experience

## Estimate
2-3 hours

## Dependencies
- Issue #8: Content Translation
- Issue #13: Quiz Creation (from Epic 5)
- Issue #7: Python AI Service

## Related Issues
- Completes the full translation experience
- Enhances Issue #14: Quiz Taking for international students