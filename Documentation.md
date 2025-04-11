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
