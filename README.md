# TravelBuddy — MERN Travel Planner

A full-stack MERN (MongoDB, Express, React, Node) travel planner application for browsing destinations, hotels, packages, and managing bookings and user profiles.

## Features
- Browse destinations, hotels, and travel packages
- User authentication (register / login) with JWT
- Create and manage bookings for hotels, transportation, and packages
- User profile and wishlist management
- Admin dashboard for managing listings and bookings

## Tech Stack
- Frontend: React (Vite)
- Backend: Node.js, Express
- Database: MongoDB (Mongoose)
- Authentication: JSON Web Tokens (JWT)
- Dev tooling: Nodemon, ESLint, Vite

## Architecture
The project is split into two folders at the repository root:
- `backend/` — Express API, Mongoose models, routes, middleware
- `frontend/` — React app (Vite) and static assets

## Getting Started
Prerequisites:
- Node.js (v18+ recommended)
- npm
- MongoDB (local or hosted URI)

Clone the repository and install dependencies for both servers.

Backend

1. Change to the backend directory and install:

```
cd backend
npm install
```

2. Create a `.env` file in `backend/` with the following variables:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000
```

3. Seed the database (optional):

```
node seed.js
```

4. Run the backend in development:

```
npm run dev
```

Available backend scripts (see `backend/package.json`):

- `npm start` — start production server (`node index.js`)
- `npm run dev` — start dev server with `nodemon`

Frontend

1. Change to the frontend directory and install:

```
cd frontend
npm install
```

2. Configure the frontend to point to your API (if needed) — adjust `src/api.js` or environment variables.

3. Run the frontend in development:

```
npm run dev
```

Common frontend scripts (see `frontend/package.json`):

- `npm run dev` — start Vite dev server
- `npm run build` — build production assets
- `npm run preview` — locally preview production build

Full dev workflow (from repository root):

```
# in separate terminals
cd backend && npm install && npm run dev
cd frontend && npm install && npm run dev
```

## Docker
Dockerfiles are provided for both services. You can build and run images separately or use a docker-compose setup (not included here).

Example: build and run backend image

```
cd backend
docker build -t travelbuddy-backend .
docker run -e MONGO_URI=your_mongo_uri -e JWT_SECRET=secret -p 5000:5000 travelbuddy-backend
```

Example: build and run frontend image

```
cd frontend
docker build -t travelbuddy-frontend .
docker run -p 5173:5173 travelbuddy-frontend
```

## Database seeding
The repository includes `seed.js` in `backend/` to populate initial data for destinations, hotels, and packages. Run `node seed.js` from the `backend` folder after configuring `MONGO_URI`.

## Project Structure

- `backend/`
    - `index.js` — server entry
    - `routes/` — Express routes (auth, destinations, hotels, packages, bookings)
    - `models/` — Mongoose models
    - `middleware/` — auth middleware
    - `seed.js` — initial data seeding script

- `frontend/`
    - `src/` — React source (components, pages, context)
    - `public/` — static assets
    - `vite.config.js` — Vite config

## Environment Variables
- `MONGO_URI` — MongoDB connection string
- `JWT_SECRET` — secret used to sign JWTs
- `PORT` — backend server port (default 5000)

## Testing
There are no automated tests included. For manual verification:
- Start backend and frontend (see Getting Started)
- Register a user, browse listings, and create bookings

## Contributing
Contributions are welcome. Typical workflow:

1. Fork the repository
2. Create a feature branch
3. Open a pull request with a clear description of changes

Please follow the existing code style and keep changes focused.


## Contact
For questions or collaboration, open an issue or contact the project owner.

