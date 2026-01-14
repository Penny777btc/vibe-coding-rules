# Master Rules

> Core rules that apply to all projects. Read this first.

---

## How to Use This File

AI assistants should read this file at the start of every project. These are universal rules learned from past mistakes.

---

## Rules

### 1. Always Handle Timezone Explicitly

- **Level**: Required
- **Problem**: Date/time bugs in production due to timezone assumptions
- **Root Cause**: Using local time when server expects UTC, or vice versa
- **Solution**:
  1. Store all timestamps in UTC
  2. Convert to user's timezone only for display
  3. Use explicit timezone conversion functions
- **Code Example**:
  ```typescript
  // Bad - assumes local timezone
  const now = new Date()

  // Good - explicit UTC
  const nowUTC = new Date().toISOString()

  // Good - explicit timezone conversion for display
  const userTime = formatInTimeZone(date, userTimezone, 'yyyy-MM-dd HH:mm')
  ```

---

### 2. Validate User Input at Boundaries

- **Level**: Required
- **Problem**: Invalid data causing crashes or security issues
- **Root Cause**: Trusting user input without validation
- **Solution**: Validate all external input at API boundaries
- **Code Example**:
  ```typescript
  // Bad - trusting input
  const userId = req.body.userId
  await db.users.delete(userId)

  // Good - validate first
  const { userId } = validateInput(req.body, userIdSchema)
  if (!userId) return res.status(400).json({ error: 'Invalid userId' })
  await db.users.delete(userId)
  ```

---

### 3. Handle Errors Gracefully

- **Level**: Required
- **Problem**: App crashes or shows cryptic errors to users
- **Root Cause**: Unhandled exceptions or missing error boundaries
- **Solution**:
  1. Wrap async operations in try-catch
  2. Log errors for debugging
  3. Show user-friendly messages
- **Code Example**:
  ```typescript
  // Bad - unhandled error
  const data = await fetch(url).then(r => r.json())

  // Good - proper error handling
  try {
    const response = await fetch(url)
    if (!response.ok) throw new Error(`HTTP ${response.status}`)
    const data = await response.json()
    return data
  } catch (error) {
    console.error('Fetch failed:', error)
    throw new UserFacingError('Unable to load data. Please try again.')
  }
  ```

---

## Adding New Rules

When you encounter a bug that could happen in any project:

1. Document it following the format above
2. Use `templates/REVIEW_PROMPT.md` to check quality
3. Add to the appropriate file:
   - Universal issues → `MASTER_RULES.md`
   - Tech-specific → `by-stack/[tech].md`
   - Problem-type specific → `by-category/[type].md`
