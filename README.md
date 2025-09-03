# Habit Tracker 📈

A cross-platform, mobile-friendly web application for tracking daily habits with visual progress indicators and streak counters.

## ✨ Features

### Core Functionality
- **Add/Delete Habits**: Simple form to add new habits and delete button for each habit
- **Daily Check-offs**: Checkbox for each habit to mark completion for today
- **GitHub-style Heatmap**: Visual calendar showing activity levels with color intensity based on completion rate
- **Streak Counter**: Shows consecutive days for each habit with a fire emoji 🔥
- **Statistics Dashboard**: Displays total habits, completed today, and longest streak

### Design Features
- **Mobile-Friendly**: Responsive grid layout that adapts to different screen sizes
- **Modern UI**: Beautiful gradient background, smooth animations, and hover effects
- **Interactive Heatmap**: Hover over any day to see the date and completion count
- **Color-Coded Activity Levels**: From light green (low activity) to dark green (high activity)

### Data Persistence
Currently uses localStorage to simulate a database. Your data persists between sessions on the same browser.

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn

### Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/my-habit-tracker.git
cd my-habit-tracker

# Install dependencies
npm install

# Start the development server
npm start
```

The app will open in your browser at `http://localhost:3000`.

## 🏗️ Backend Implementation (Future)

To connect this to a real database backend, the following components will be needed:

### Database Schema
```sql
-- Users table
CREATE TABLE users (
    id UUID PRIMARY KEY,
    email VARCHAR(255) UNIQUE,
    created_at TIMESTAMP
);

-- Habits table
CREATE TABLE habits (
    id UUID PRIMARY KEY,
    user_id UUID REFERENCES users(id),
    name VARCHAR(255),
    created_at TIMESTAMP
);

-- Completions table
CREATE TABLE completions (
    id UUID PRIMARY KEY,
    habit_id UUID REFERENCES habits(id),
    completed_date DATE,
    created_at TIMESTAMP,
    UNIQUE(habit_id, completed_date)
);
```

### API Endpoints
- `GET /api/habits` - Fetch all habits for a user
- `POST /api/habits` - Create a new habit
- `DELETE /api/habits/:id` - Delete a habit
- `GET /api/completions` - Get all completions
- `POST /api/completions` - Mark habit as complete
- `DELETE /api/completions` - Mark habit as incomplete

### Authentication
- JWT or session-based auth
- Login/signup pages
- Secure API endpoints

## 📱 Technologies Used

- **Frontend**: React, CSS3, JavaScript
- **Storage**: localStorage (temporary)
- **Future Backend**: Node.js/Express + PostgreSQL/MySQL
- **Deployment**: Vercel/Netlify (frontend), Heroku/Railway (backend)

## 🎯 Roadmap

- [ ] User authentication system
- [ ] Backend API with database integration
- [ ] User accounts and data sync
- [ ] Habit categories and tags
- [ ] Export data functionality
- [ ] Progressive Web App (PWA) features
- [ ] Push notifications for habit reminders

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
