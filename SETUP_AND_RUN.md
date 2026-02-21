# PulseChain - Complete Setup & Run Guide

This guide walks you through setting up and running the entire PulseChain application (Frontend + Backend + Database).

## 📋 Prerequisites

Before you start, ensure you have installed:
- **Node.js** 14+ ([Download](https://nodejs.org/))
- **PostgreSQL** 12+ ([Download](https://www.postgresql.org/download/))
- **Git** (optional, for version control)

Verify installations:
```bash
node --version
npm --version
psql --version
```

---

## 🗄️ Part 1: Database Setup

### Step 1: Create PostgreSQL Database

Open PowerShell or Command Prompt and connect to PostgreSQL:

```bash
psql -U postgres
```

You'll be prompted for the PostgreSQL password you set during installation.

### Step 2: Create the Database

In the PostgreSQL prompt, run:

```sql
CREATE DATABASE pulsechain;
```

Verify it was created:
```sql
\l
```

You should see `pulsechain` in the list. Exit PostgreSQL:
```sql
\q
```

### Step 3: Initialize Database Schema

Navigate to the backend directory and run the schema:

```bash
cd c:\tinkerhack\pulsechain-backend
psql -U postgres -d pulsechain -f database/schema.sql
```

This creates all tables, indexes, and constraints. You should see no errors.

Verify tables were created:
```bash
psql -U postgres -d pulsechain -c "\dt"
```

You should see these 8 tables:
- `users`
- `donations`
- `blood_requests`
- `request_responses`
- `notifications`
- `leaderboard`
- `user_preferences`
- `achievement_badges` (optional)

---

## 🔧 Part 2: Backend Setup

### Step 1: Navigate to Backend Directory

```bash
cd c:\tinkerhack\pulsechain-backend
```

### Step 2: Install Dependencies

```bash
npm install
```

This installs all required packages (Express, PostgreSQL client, JWT, bcrypt, etc.).

### Step 3: Configure Environment Variables

Open `.env` file and update with your actual values:

```env
# Database Configuration
DATABASE_URL=postgresql://postgres:your_password@localhost:5432/pulsechain

# Server Configuration
PORT=5000
NODE_ENV=development

# JWT Security (change to a strong random string)
JWT_SECRET=your_super_secret_jwt_key_change_this_in_production

# Email Configuration (optional, for notifications)
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password
```

**Important**: Replace `your_password` with your actual PostgreSQL password.

### Step 4: Verify Backend Runs

Start the backend in development mode:

```bash
npm run dev
```

You should see:
```
Server running on http://localhost:5000
Connected to database
```

### Step 5: Test API Health Check

Open a new PowerShell window and run:

```bash
curl http://localhost:5000/health
```

You should get:
```json
{"status":"ok"}
```

**Keep the backend running** (don't close this terminal). Open a new terminal for the frontend.

---

## ⚛️ Part 3: Frontend Setup

### Step 1: Open New Terminal

Open a new PowerShell window and navigate to frontend:

```bash
cd c:\tinkerhack\pulsechain-frontend
```

### Step 2: Install Dependencies

```bash
npm install
```

### Step 3: Configure Environment (Optional)

Create a `.env` file in the frontend directory:

```env
REACT_APP_API_URL=http://localhost:5000/api
```

(This is the default, but explicitly setting it helps with deployment)

### Step 4: Start Frontend Development Server

```bash
npm start
```

The app will automatically open in your browser at `http://localhost:3000`.

If it doesn't open automatically, navigate to: **http://localhost:3000**

---

## ✅ Verify Everything Works

### 1. Frontend Loads
- You should see the PulseChain home page with red gradient styling
- Navigation bar with Home, Donor, Seeker, Leaderboard, Settings links

### 2. Test User Registration
1. Click "Register" or navigate to `/register`
2. Fill in the form:
   - Name: Test User
   - Email: test@example.com
   - Password: Test@123
   - Phone: 1234567890
   - Blood Group: O+
   - Role: Donor
3. Click Register
4. You should be redirected to Home page (or can login now)

### 3. Test User Login
1. Click "Login" or navigate to `/login`
2. Enter credentials:
   - Email: test@example.com
   - Password: Test@123
3. Click Login
4. You should see your dashboard

### 4. Backend Database Check
In a new PowerShell, check if user was created:

```bash
psql -U postgres -d pulsechain -c "SELECT id, name, email, blood_group, role FROM users;"
```

You should see your test user in the list.

---

## 🚀 Running the Complete Application

### Option 1: Two Separate Terminals (Recommended)

**Terminal 1 - Backend:**
```bash
cd c:\tinkerhack\pulsechain-backend
npm run dev
```

**Terminal 2 - Frontend:**
```bash
cd c:\tinkerhack\pulsechain-frontend
npm start
```

Both servers will run simultaneously.

### Option 2: Single Terminal (Sequential)

**Start Backend:**
```bash
cd c:\tinkerhack\pulsechain-backend
npm run dev
```

Then in another terminal:

**Start Frontend:**
```bash
cd c:\tinkerhack\pulsechain-frontend
npm start
```

### Option 3: Background Process (Advanced)

In PowerShell, run backend as background job:

```bash
cd c:\tinkerhack\pulsechain-backend
Start-Job -ScriptBlock { npm run dev }

# Then in same terminal
cd c:\tinkerhack\pulsechain-frontend
npm start
```

---

## 📊 Application URLs

Once running:

| Component | URL | Purpose |
|-----------|-----|---------|
| Frontend | http://localhost:3000 | React app UI |
| Backend API | http://localhost:5000 | API endpoints |
| Health Check | http://localhost:5000/health | Server status |
| Database | localhost:5432 | PostgreSQL |

---

## 📝 Key Endpoints to Test

### Authentication
```bash
# Register
curl -X POST http://localhost:5000/api/users/register \
  -H "Content-Type: application/json" \
  -d '{"name":"John","email":"john@example.com","password":"Test@123","phone":"9876543210","blood_group":"O+","role":"donor"}'

# Login
curl -X POST http://localhost:5000/api/users/login \
  -H "Content-Type: application/json" \
  -d '{"email":"john@example.com","password":"Test@123"}'
```

Copy the `token` from login response for protected endpoints.

### Protected Endpoints (require Authorization header)
```bash
# Get User Profile
curl -H "Authorization: Bearer {token}" \
  http://localhost:5000/api/users/profile

# Create Blood Request
curl -X POST http://localhost:5000/api/blood-requests \
  -H "Authorization: Bearer {token}" \
  -H "Content-Type: application/json" \
  -d '{"blood_group":"O+","blood_units":2,"hospital":"City Hospital","urgency_level":"urgent","latitude":11.8745,"longitude":75.3704}'

# Get Leaderboard
curl http://localhost:5000/api/leaderboard
```

---

## 🐛 Troubleshooting

### Issue: "Port 3000 already in use"
**Solution**: Change frontend port:
```bash
set PORT=3001
npm start
```
Then access at `http://localhost:3001`

### Issue: "Port 5000 already in use"
**Solution**: Change backend port in `.env`:
```env
PORT=5001
```
Then update frontend `.env`:
```env
REACT_APP_API_URL=http://localhost:5001/api
```

### Issue: "Database connection error"
**Solution**: 
1. Verify PostgreSQL is running
2. Check DATABASE_URL in `.env` matches your setup
3. Verify database exists: `psql -U postgres -l | grep pulsechain`
4. Check username/password are correct

### Issue: "Module not found errors"
**Solution**:
```bash
# Clear node_modules and reinstall
rm -r node_modules
npm install
```

### Issue: "npm: command not found"
**Solution**: Node.js not installed or not in PATH. Reinstall Node.js and restart terminal.

### Issue: "psql: command not found"
**Solution**: PostgreSQL not in PATH. Add PostgreSQL bin to PATH or use full path to psql.

---

## 📱 Features to Try

Once everything is running:

1. **Register as Donor** - Create donor account, set blood group and location
2. **Register as Seeker** - Create seeker account, search for donors
3. **View Map** - See donor locations on interactive map
4. **Search Donors** - Filter by blood group, search by name
5. **View Leaderboard** - See top donors and your ranking
6. **Settings** - Configure notification preferences
7. **Create Blood Request** - As seeker, request blood from donors

---

## 🔒 Security Notes

⚠️ **Development vs Production**:

### Development (.env):
- `JWT_SECRET`: Simple key (change before production)
- `NODE_ENV`: development
- Database SSL: Disabled for local testing

### Production (when deploying):
- `JWT_SECRET`: Generate strong random string
- `NODE_ENV`: production
- `DATABASE_URL`: Use deployed database URL
- Enable SSL/HTTPS
- Use environment variables from deployment platform

---

## 📚 Further Setup

### Real-time Notifications (Socket.io)
The backend is prepared for Socket.io. To enable:

1. Install socket.io client in frontend:
```bash
cd pulsechain-frontend
npm install socket.io-client
```

2. Update your components to connect to WebSocket:
```javascript
import io from 'socket.io-client';

const socket = io('http://localhost:5000');
socket.on('notification', (data) => {
  console.log('New notification:', data);
});
```

### Email Notifications
Configure in `.env`:
```env
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password  # Use Gmail app password if 2FA enabled
```

---

## 🎯 Next Steps

1. ✅ Run both servers as described above
2. ✅ Register test accounts
3. ✅ Explore all pages and features
4. ✅ Test API endpoints
5. 📋 Read individual README files for more details:
   - [Frontend README](./pulsechain-frontend/README.md)
   - [Backend README](./pulsechain-backend/README.md)

---

## 💡 Quick Reference

```bash
# Start Everything (use separate terminals)

# Terminal 1: Start PostgreSQL (if not running as service)
# Usually not needed on Windows if installed as service

# Terminal 2: Start Backend
cd c:\tinkerhack\pulsechain-backend
npm run dev

# Terminal 3: Start Frontend
cd c:\tinkerhack\pulsechain-frontend
npm start
```

---

## ❓ Need Help?

- Check backend logs in Terminal 2 for API errors
- Check browser console (F12) in Terminal 3 for frontend errors
- Verify database: `psql -U postgres -d pulsechain -c "\dt"`
- Check connections: `netstat -ano | findstr :3000` and `netstat -ano | findstr :5000`

---

**Happy coding! 🚀**

Built with ❤️ for the PulseChain community
