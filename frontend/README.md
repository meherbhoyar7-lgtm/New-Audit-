# Audit Dashboard Frontend

React-based frontend for the Activity Log and Audit Trail Dashboard system.

## Features

- **Dashboard**: Overview of activity statistics and trends
- **Activity Logs**: View all user and system activities with filtering
- **Audit Trail**: Track detailed changes and modifications
- **Semantic Search**: Intelligent search across logs and audit trails
- **Real-time Updates**: Live data from backend API

## Tech Stack

- React 18
- React Router v6
- Tailwind CSS
- Recharts for visualizations
- Zustand for state management
- Axios for API calls
- date-fns for date formatting

## Setup & Installation

```bash
cd frontend
npm install
npm start
```

The app runs on `http://localhost:3000`

## API Endpoints

All API calls go to `http://localhost:8080/api`

### Activity Logs
- `GET /activity-logs` - Get all activity logs
- `GET /activity-logs/{id}` - Get specific log
- `POST /activity-logs` - Create new log
- `PUT /activity-logs/{id}` - Update log
- `DELETE /activity-logs/{id}` - Delete log
- `GET /activity-logs/user/{userId}` - Get logs by user
- `GET /activity-logs/date-range` - Filter by date range
- `GET /activity-logs/filter/action` - Filter by action

### Audit Trail
- `GET /audit-trails` - Get all audit trails
- `GET /audit-trails/{id}` - Get specific audit
- `POST /audit-trails` - Create new audit entry
- `GET /audit-trails/entity` - Get by entity
- `GET /audit-trails/change-type` - Filter by change type

### Semantic Search
- `POST /semantic-search` - Global search
- `POST /semantic-search/activity-logs` - Search activity logs
- `POST /semantic-search/audit-trails` - Search audit trails

### Analytics
- `GET /analytics/activity-summary` - Activity statistics
- `GET /analytics/user-stats/{userId}` - User-specific stats
- `GET /analytics/trends` - Activity trends
- `GET /analytics/action-statistics` - Action breakdown

### Filters
- `GET /filters/options` - Get available filter options
- `POST /filters/apply` - Apply complex filters

## Project Structure

```
frontend/
├── src/
│   ├── components/        # Reusable React components
│   │   ├── Navigation.jsx
│   │   ├── Card.jsx
│   │   ├── Pagination.jsx
│   │   ├── LoadingSpinner.jsx
│   │   ├── ErrorMessage.jsx
│   │   └── FilterPanel.jsx
│   ├── pages/            # Page components
│   │   ├── Dashboard.jsx
│   │   ├── ActivityLogs.jsx
│   │   ├── AuditTrail.jsx
│   │   └── SemanticSearch.jsx
│   ├── services/         # API service layer
│   │   └── api.js
│   ├── store/            # Zustand state stores
│   │   └── store.js
│   ├── App.jsx
│   ├── index.jsx
│   └── index.css
├── public/
│   └── index.html
├── package.json
├── tailwind.config.js
└── postcss.config.js
```

## Available Scripts

- `npm start` - Start development server
- `npm build` - Build for production
- `npm test` - Run tests
- `npm eject` - Eject from create-react-app (irreversible)

## Environment Configuration

The frontend connects to the backend API at `http://localhost:8080/api`

To change the API base URL, edit `frontend/src/services/api.js`:

```javascript
const API_BASE_URL = 'http://localhost:8080/api';
```

## Features in Detail

### Dashboard
- Real-time activity summary
- Activity trends chart
- Action statistics visualization
- Key metrics cards

### Activity Logs
- Paginated list of all activities
- Filter by action, user, date range
- Detailed activity information
- Timestamp and IP tracking

### Audit Trail
- Complete change history
- Entity-based tracking
- Severity levels
- Change type categorization

### Semantic Search
- Natural language queries
- Example search suggestions
- Multi-type search (All, Activity Logs, Audit Trails)
- Relevance scoring

## Performance Considerations

- Pagination for large datasets (default 20 items/page)
- Debounced search queries
- Optimized re-renders with Zustand
- Lazy loading of charts
- Memoized components

## Future Enhancements

- Export logs to CSV/PDF
- Real-time WebSocket updates
- Advanced analytics
- Custom dashboard widgets
- User preferences storage
- Dark mode support
