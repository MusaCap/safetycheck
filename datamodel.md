# SafeQuest – Data Model

## Entities and Relationships

---

## 1. User

### Attributes
- `user_id` (UUID, PK)
- `username` (String)
- `email` (String, unique, optional for kids)
- `password_hash` (String)
- `role` (Enum: 'child', 'parent', 'educator')
- `created_at` (Timestamp)
- `last_login` (Timestamp)
- `is_active` (Boolean)

### Relationships
- One-to-many with `PlayerProfile` (children)
- One-to-one or many-to-one with `ParentProfile`

---

## 2. PlayerProfile

### Attributes
- `profile_id` (UUID, PK)
- `user_id` (UUID, FK to User)
- `nickname` (String)
- `avatar_url` (String)
- `age` (Integer)
- `grade_level` (String)
- `city` (String)
- `current_score` (Integer)
- `badges_earned` (JSON)
- `quests_completed` (Integer)

### Relationships
- One-to-many with `GameSession`
- One-to-many with `SafetyModuleProgress`

---

## 3. ParentProfile

### Attributes
- `parent_id` (UUID, PK)
- `user_id` (UUID, FK to User)
- `child_profiles` (Array of UUIDs)
- `notifications_enabled` (Boolean)
- `dashboard_preferences` (JSON)

### Relationships
- One-to-many with `PlayerProfile`

---

## 4. SafetyModule

### Attributes
- `module_id` (UUID, PK)
- `title` (String)
- `category` (Enum: 'Stranger Danger', 'Fire Safety', 'Environment', 'Bullying', 'Digital Safety')
- `description` (Text)
- `difficulty_level` (Enum: 'Easy', 'Medium', 'Hard')
- `content_json` (JSON or linked media)
- `is_active` (Boolean)

### Relationships
- One-to-many with `SafetyModuleProgress`
- One-to-many with `MiniGame`

---

## 5. SafetyModuleProgress

### Attributes
- `progress_id` (UUID, PK)
- `profile_id` (UUID, FK to PlayerProfile)
- `module_id` (UUID, FK to SafetyModule)
- `status` (Enum: 'Not Started', 'In Progress', 'Completed')
- `score` (Integer)
- `time_spent_minutes` (Float)
- `last_accessed` (Timestamp)

---

## 6. GameSession

### Attributes
- `session_id` (UUID, PK)
- `profile_id` (UUID, FK to PlayerProfile)
- `module_id` (UUID, FK to SafetyModule)
- `start_time` (Timestamp)
- `end_time` (Timestamp)
- `correct_decisions` (Integer)
- `incorrect_decisions` (Integer)
- `rewards_earned` (JSON)

---

## 7. MiniGame

### Attributes
- `minigame_id` (UUID, PK)
- `module_id` (UUID, FK to SafetyModule)
- `name` (String)
- `description` (Text)
- `media_url` (String)
- `is_timed` (Boolean)
- `max_score` (Integer)

---

## 8. Badge

### Attributes
- `badge_id` (UUID, PK)
- `name` (String)
- `description` (Text)
- `criteria` (JSON)
- `icon_url` (String)

### Relationships
- Many-to-many with `PlayerProfile` (via `PlayerBadge`)

---

## 9. PlayerBadge

### Attributes
- `player_badge_id` (UUID, PK)
- `profile_id` (UUID, FK to PlayerProfile)
- `badge_id` (UUID, FK to Badge)
- `awarded_at` (Timestamp)

---

## 10. Feedback & Reports

### Attributes
- `feedback_id` (UUID, PK)
- `user_id` (UUID, FK to User)
- `type` (Enum: 'bug', 'suggestion', 'general')
- `message` (Text)
- `submitted_at` (Timestamp)
- `status` (Enum: 'Open', 'Reviewed', 'Resolved')

---
