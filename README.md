# Job Application Email Manager

A full‑stack web application to manage HR contact lists and send job‑application emails with CV attachments in safe, compliant batches.

## Features
- Import contacts from CSV/Excel with validation and duplicate detection
- Email template creator with placeholders (`{{HRName}}`, `{{CompanyName}}`, `{{CandidateName}}`)
- CV upload (PDF/DOCX) validation
- Configurable SMTP integration (encrypted credentials)
- Batch email sending respecting hourly/daily limits and delay between messages
- Logging, unsubscribe handling and audit trail
- Simple email/password authentication (JWT)
- Premium UI with dark‑mode, glass‑morphism and smooth micro‑animations (vanilla HTML/CSS/JS)

## Tech Stack (defaults)
- **Backend**: Node.js / Express
- **Database**: SQLite (file‑based) via Sequelize ORM
- **Frontend**: Vanilla HTML, CSS and JavaScript (no framework)
- **Email**: Nodemailer
- **Auth**: bcryptjs + JSON Web Tokens

## Quick Start
```bash
# Step 1: create project folder (already created for you)
cd "C:/Users/DELL/Desktop/Job/job-email-manager"

# Step 2: install dependencies
npm install

# Step 3: run development server
npm run dev
```

The server will start on **http://localhost:3000** and the frontend can be opened via the same URL.

## Folder Structure
```
job-email-manager/
├─ backend/
│  ├─ src/
│  │  ├─ index.js            # Express entry point
│  │  ├─ routes/            # API route definitions
│  │  ├─ controllers/       # Business logic
│  │  ├─ models/            # Sequelize models
│  │  └─ services/          # CSV import, email, batch scheduler, auth
│  ├─ config/               # Config files (env, DB, SMTP)
│  └─ migrations/          # DB migration scripts
├─ frontend/
│  ├─ public/               # Uploaded CVs, static assets
│  └─ src/
│     ├─ index.html
│     ├─ styles.css
│     └─ app.js
├─ docs/
│  ├─ database_schema.md
│  └─ api_spec.md
├─ .gitignore
└─ package.json
```

## Development
- API documentation is available at **http://localhost:3000/api-docs** (Swagger UI).
- Frontend interacts with the API using the bundled `app.js`.
- Run `npm run lint` to check code style.

---
*All sensitive values (SMTP password) are stored encrypted on the server; the frontend never receives raw credentials.*
