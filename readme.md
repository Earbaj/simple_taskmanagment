## Simple Task Management (Node.js + MongoDB)

This is a basic task management application built with Node.js, Express, and MongoDB.

Below are quick instructions to add environment variables and run the app locally.

## Environment variables

Create a file named `.env` in the project root (same folder as `server.js`). At minimum include:

```
MONGO_URI=mongodb://localhost:27017/simple_task_management
PORT=5000
# optional: NODE_ENV=development
```

- If you prefer Atlas, use your Atlas connection string for `MONGO_URI` (keep credentials secure).
- Make sure `.env` is listed in `.gitignore` (do not commit secrets).

## Install dependencies

Install packages with npm:

```bash
npm install
```

Note: The `start` script in `package.json` uses `nodemon` (`npm start`). If you don't have `nodemon` installed globally, either install it as a dev dependency:

```bash
npm install --save-dev nodemon
```

or run the server directly with:

```bash
node server.js
```

## Start MongoDB (if using a local MongoDB)

- On many Linux systems with the official package:

```bash
sudo systemctl start mongod
```

- Or run `mongod` directly if you installed MongoDB manually.
- If using MongoDB Atlas, ensure your `MONGO_URI` contains credentials and allows connections from your IP.

## Run the app

Start the server:

```bash
npm start
# or
node server.js
```

By default the server listens on `process.env.PORT` or `5000` if not set. When running, you should see a message like:

```
🚀 Server running on port 5000
✅ MongoDB Connected
```

## Test the API

After the server is running, open or call the API. Example: get all tasks

```bash
curl http://localhost:5000/api/tasks
```

Or use your browser / Postman to interact with the routes under `/api/tasks`:
- POST `/api/tasks` to create
- GET `/api/tasks` to list
- PUT `/api/tasks/:id` to update
- DELETE `/api/tasks/:id` to remove

## Notes and troubleshooting

- If connection to MongoDB fails, double-check `MONGO_URI` and that MongoDB is running.
- If `npm start` fails because `nodemon` is missing, either install it or use `node server.js`.
- For production, use a process manager (pm2, systemd) and secure environment variable storage.

---

If you'd like, I can also add a `.env.example` file and a short script to seed example tasks.

