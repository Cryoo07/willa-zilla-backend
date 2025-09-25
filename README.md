## Willa-Zilla Backend

Express + MongoDB backend API.

### Prerequisites

- Node.js 18+ and npm
- MongoDB (local or a cloud URI)

### Project structure

```text
backendAss2/
  index.js
  package.json
  package-lock.json
  src/
    configs/
      config.js
      db.js
    controllers/
      userController.js
    middleware/
    models/
    routes/
    services/
```

### Environment variables

Create a `.env` file in the project root:

```bash
# Server
PORT=3000

# MongoDB
DB_URL=mongodb://localhost:27017/willa-zilla
```

Notes:

- `PORT` defaults to `3000` if not provided.
- `DB_URL` defaults to `mongodb://localhost:27017/willa-zilla` if not provided.

### Install

```bash
npm install
```

### Run (development)

```bash
npm run dev
```

Starts with nodemon, auto-restarts on file changes.

### Run (production)

```bash
npm start
```

### Health check

- GET `/health` → `{ "status": "ok" }`

### MongoDB connection

Connection string is read from `DB_URL` and initialized in `index.js`.

### Common issues

- Ensure MongoDB is running or `DB_URL` points to a reachable cluster.
- Windows PowerShell example to set a one-off variable for the current command:

```powershell
$env:DB_URL="mongodb://localhost:27017/willa-zilla"; npm run dev
```

### Scripts

- `npm run dev` → `nodemon index.js`
- `npm start` → `node index.js`

### License

MIT
