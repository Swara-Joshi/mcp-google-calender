# Google Calendar Integration with Claude via MCP Server

A Model Context Protocol (MCP) server for Google Calendar integration with AI assistants.

**Created by:** Rishil Trivedi and Swara Joshi

## Available Functions

| Function | Description |
|----------|-------------|
| `list-calendars` | List all available calendars |
| `list-events` | List events with date filtering |
| `search-events` | Search events by text query |
| `create-event` | Create new calendar events |
| `update-event` | Update existing events |
| `delete-event` | Delete events |
| `get-freebusy` | Check availability across calendars |
| `list-colors` | List available event colors |

## Setup Steps

### Prerequisites
1. Google Cloud project with Calendar API enabled
2. OAuth 2.0 credentials (Desktop app type)

### Google Cloud Setup
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create/select project
3. Enable [Google Calendar API](https://console.cloud.google.com/apis/library/calendar-json.googleapis.com)
4. Create OAuth 2.0 credentials:
   - Go to Credentials → "Create Credentials" → "OAuth client ID"
   - Choose "User data" type
   - Add app name and contact info
   - Select "Desktop app" as application type
   - Add email as test user in Audience screen

### Installation Options

**Option 1: NPX (Recommended)**
```json
{
  "mcpServers": {
    "google-calendar": {
      "command": "npx",
      "args": ["@cocal/google-calendar-mcp"],
      "env": {
        "GOOGLE_OAUTH_CREDENTIALS": "/path/to/your/gcp-oauth.keys.json"
      }
    }
  }
}
```

**Option 2: Local Installation**
```bash
git clone https://github.com/nspady/google-calendar-mcp.git
cd google-calendar-mcp
npm install
npm run build
```

### Configuration Files
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

### First Run
1. Start Claude Desktop
2. Complete OAuth flow in browser
3. Ready to use calendar features

## Key Features
- Multi-calendar support
- Event management (CRUD operations)
- Recurring events handling
- Free/busy queries
- Smart scheduling with natural language
- Image-based event import (PNG, JPEG, GIF)
