# InterviewPro - Online Interview Platform

A comprehensive web application for conducting online technical interviews with real-time monitoring and anti-cheat features.

## Features

### Admin Panel
- **Dashboard**: Real-time analytics with charts showing test attempts, completion rates, and performance metrics
- **Question Management**: Create and manage MCQ and coding questions with different difficulty levels
- **Candidate Management**: Add candidates and send secure test invitations
- **Campaign Management**: Create interview campaigns with customizable duration and question types
- **Attempt Tracking**: Monitor all test attempts with detailed analytics and CSV export

### Candidate Test Interface
- **Secure Access**: Unique token-based links for each test session
- **Multiple Question Types**: Support for both MCQ and coding questions
- **Real-time Timer**: Countdown timer with auto-submission
- **Code Editor**: Built-in code editor for programming challenges
- **Anti-cheat Features**: Tab switch detection, disabled copy/paste, right-click protection

### Security Features
- **Authentication**: Supabase Auth for admin login
- **Row Level Security**: Database-level access control
- **Anti-cheat Monitoring**: Track tab switches and suspicious behavior
- **Secure Tokens**: Cryptographically secure test links
- **Session Management**: Automatic session handling and cleanup

## Technology Stack

- **Frontend**: Pure HTML, CSS, and Vanilla JavaScript (ES6 modules)
- **Backend**: Supabase (Database, Auth, Edge Functions)
- **Charts**: Chart.js for analytics visualization
- **Email**: Resend API for sending test invitations
- **Deployment**: Static hosting compatible

## Quick Start

1. **Setup Supabase**: Click "Connect to Supabase" button in the top right
2. **Run Migrations**: The database schema will be automatically created
3. **Configure Email**: Add your Resend API key to environment variables (optional)
4. **Create Admin User**: Register an admin account through Supabase dashboard
5. **Start Testing**: Access admin panel and begin creating questions and campaigns

## Database Schema

- **questions**: Store all test questions (MCQ and coding)
- **candidates**: Manage candidate information
- **campaigns**: Define interview rounds and settings
- **invites**: Secure token-based test invitations
- **attempts**: Track all test sessions and results

## File Structure

```
├── index.html          # Admin login page
├── admin.html          # Admin dashboard
├── test.html           # Candidate test interface
├── css/
│   └── style.css       # Complete responsive styling
├── js/
│   ├── supabase.js     # Supabase client and helpers
│   ├── login.js        # Admin authentication
│   ├── admin.js        # Admin panel functionality
│   ├── test.js         # Candidate test logic
│   ├── utils.js        # Utility functions
│   └── charts.js       # Chart configurations
└── supabase/
    ├── migrations/     # Database schema
    └── functions/      # Edge functions for email
```

## Usage

### For Administrators
1. Login at `/index.html`
2. Create questions in the Questions section
3. Add candidates in the Candidates section
4. Create campaigns in the Campaigns section
5. Send test invitations to candidates
6. Monitor attempts and export results

### For Candidates
1. Open the unique test link received via email
2. Read instructions and start the test
3. Answer questions within the time limit
4. Submit the test when complete

## Anti-cheat Features

- **Tab Switch Detection**: Warns and tracks when candidates leave the test window
- **Disabled Interactions**: Copy/paste, right-click, and print are disabled
- **Timer Enforcement**: Automatic submission when time expires
- **Session Monitoring**: Tracks all suspicious activities

## Customization

The platform is built with modularity in mind. You can easily:
- Add new question types
- Customize scoring algorithms
- Integrate additional email providers
- Add new chart types for analytics
- Extend anti-cheat features

## Security Notes

- All database access is protected by Row Level Security (RLS)
- Admin authentication required for management functions
- Candidate access is token-based with single-use links
- No sensitive data is stored in localStorage or client-side