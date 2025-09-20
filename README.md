# TicTacToe.NET-Tournament

Description
-----------
Create a web-based tic-tac-toe tournament app. Front-end is handled by React and the back-end is built with ASP.NET Core.

## Tech Stack
- ASP.NET Core
- React

## Requirements
- Bracket Management API (Hint: Use RESTful routes and clear naming)
- Turn-Based Game Logic (Hint: Validate moves server-side)
- State Synchronization in React (Hint: Utilize React hooks for live updates)
- Code Quality and Testing (Hint: Follow SOLID principles and add tests)

## Installation

### Prerequisites
- .NET 6+ SDK
- Node.js 14+
- npm or yarn

### Clone the repository
bash
git clone https://github.com/yourusername/TicTacToe.NET-Tournament.git
cd TicTacToe.NET-Tournament


### Backend Setup
bash
cd backend
dotnet restore
cp appsettings.json.example appsettings.json   # or set env vars for ConnectionStrings:DefaultConnection
dotnet build


### Frontend Setup
bash
cd frontend
npm install       # or yarn install
cp .env.example .env   # set REACT_APP_API_URL=http://localhost:5000/api
npm start         # or yarn start


## Usage
1. Start the ASP.NET Core API:
   bash
   cd backend
   dotnet run
   
2. Start the React dev server:
   bash
   cd frontend
   npm start
   
3. Navigate to http://localhost:3000 to launch the tournament UI.

## Implementation Steps
1. Initialize an ASP.NET Core Web API project in `/backend`.
2. Define `BracketController` with RESTful endpoints: GET, POST, PUT, DELETE under `/api/brackets`.
3. Implement `GameController` to manage game state and validate moves at `/api/games/{gameId}`.
4. Apply SOLID design principles, add xUnit tests for controllers and services.
5. Set up React app in `/frontend` using Create React App.
6. Create bracket management UI components; fetch and mutate bracket data via `useEffect` and custom hooks.
7. Build `GameBoard` component; handle user clicks, send move requests to the API, and update state in real time.
8. Write Jest + React Testing Library tests for key UI components and game logic.

## API Endpoints

### Bracket Management
- GET    /api/brackets           -> List all brackets
- POST   /api/brackets           -> Create a new bracket
- GET    /api/brackets/{id}      -> Get bracket details
- PUT    /api/brackets/{id}      -> Update a bracket
- DELETE /api/brackets/{id}      -> Remove a bracket

### Game Moves
- GET  /api/games/{gameId}/state -> Get current game state
- POST /api/games/{gameId}/moves -> Submit a move (body: `{ "player": "X|O", "position": 0-8 }`)