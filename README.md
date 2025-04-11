# ⚙️ Cursor Setup Guide

This document outlines how to set up and manage your project efficiently using [Cursor](https://www.cursor.so).

---

## 1. 📂 File Structure

Create the following project files in your repo:

- `.cursorrules`
- `Project_milestones.md`
- `Documentation.md`

---

## 2. 🔏 .cursorrules

```yaml
Project Management:
  - Reference Project_milestones.md for all feature implementations
  - Reference Documentation.md for all API endpoints and request/response formats
  - Ensure new code aligns with defined milestones
  - Follow the established database schema
  - Consider cost optimizations defined in metrics
  - Maintain consistency with existing components

Indexing:
  - Reindex the codebase regularly via Settings → Cursor settings → Features

Workflow:
  - Work in increments: use Project_milestones.md to decide next feature
  - Update milestones and documentation after completing tasks

Documentation:
  - Keep Documentation.md updated with all public functions, schemas, API formats
```

---

## 3. 🧍‍♂️ Project_milestones.md

```md
# 📌 Project Milestones

## Phase 1: Manual Operations & Testing
- [ ] Basic API integration
- [ ] Database schema setup
- [ ] Basic OpenAI integration
- [ ] Manual data collection script
- [ ] Manual analysis trigger
- [ ] Manual review interface
- [ ] Testing and refinement

---

## Phase 2: Worker Refactoring
- [ ] Split call-worker (API + data collection)
- [ ] Split analysis-worker (OpenAI + processing)
- [ ] Split api-worker (dashboard & admin endpoints)
- [ ] Implement rate limiting
- [ ] Add error handling
- [ ] Add usage and cost tracking

---

## Learnings & Architecture Decisions

### ✅ Worker Architecture
**Current Setup**
- Single worker handling both API and OpenAI calls

**Issues**
- Harder to scale
- No isolation for error handling or rate limits
- Complex debugging

**Decision**
- Split workers:
  - `call-worker`
  - `analysis-worker`
  - `api-worker`

**Benefits**
- Modular scaling
- Easier error tracking
- Cost separation
```

---

## 4. 📚 Documentation.md

```md
# 📚 Project Documentation

## 🧠 Overview
This document keeps track of:
- API Endpoints
- Database schema
- Core functions
- Request/response formats

---

## 🧪 API Endpoints

### POST /api/submit-proposal
**Description:** Upload and validate proposal against scope document  
**Request:**
```json
{
  "proposal": "file",
  "scope": "file"
}
```
**Response:**
```json
{
  "status": "success",
  "message": "Proposal is aligned with scope."
}
```

---

## 💃 Database Schema

### Table: `proposals`
| Column        | Type       | Description                   |
|---------------|------------|-------------------------------|
| id            | UUID       | Primary Key                   |
| filename      | String     | Name of uploaded proposal     |
| scope_id      | UUID       | Foreign key to scope doc      |
| status        | String     | Status of validation          |
| created_at    | Timestamp  | Upload time                   |

---

## ⚙️ Functions

### validate_proposal(proposal: str, scope: str) → bool
Checks if the proposal covers all scope items.

### generate_summary(document: str) → str
Generates a short summary using OpenAI.
```

---

## 5. 💡 Tips & Best Practices

- Use [Awesome Cursor Rules](https://github.com/cursor-dev/awesome-cursor-rules) to enhance your `.cursorrules` file.
- Reindex the codebase from:
  > **Settings → Cursor settings → Features**
- Keep tasks small and incremental. Ask Cursor:
  > _“Let’s work on the next feature.”_
- Update `Project_milestones.md` and `Documentation.md` regularly.

---

## 6. 📺 Helpful Video Guides

- [Cursor Workflow Part 1](https://www.youtube.com/watch?v=1L509JK8p1I)
- [Cursor Deep Dive Part 2](https://www.youtube.com/watch?v=2PjmPU07KNs)

