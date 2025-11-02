# Render Deployment Guide

## Configuration for Render Services

### Frontend (Static Site)

**Service Type:** Static Site

**Configuration:**
- **Root Directory:** Leave empty (defaults to repository root)
- **Build Command:** `yarn build`
- **Publish Directory:** `client/dist`
- **Node Version:** 22.16.0 (optional, in Environment Variables)

### Backend (Web Service)

**Service Type:** Web Service

**Option A (Recommended):**
- **Root Directory:** `server`
- **Build Command:** `yarn install`
- **Start Command:** `node server.js`
- **Node Version:** 22.16.0 (optional)

**Option B (Alternative):**
- **Root Directory:** Leave empty (repository root)
- **Build Command:** `cd server && yarn install`
- **Start Command:** `cd server && node server.js`
- **Node Version:** 22.16.0 (optional)

### Required Environment Variables for Backend

- `MONGODB_URI` - Your MongoDB connection string
- `JWT_SECRET` - A secure random string for JWT tokens
- `PORT` - Set to `4000` (or Render will auto-assign)

## Quick Setup Steps

1. **Go to Render Dashboard:** https://dashboard.render.com

2. **For Frontend:**
   - Click "New" → "Static Site"
   - Connect your GitHub repository
   - Root Directory: (empty/root)
   - Build Command: `yarn build`
   - Publish Directory: `client/dist`

3. **For Backend:**
   - Click "New" → "Web Service"
   - Connect your GitHub repository
   - Root Directory: `server`
   - Build Command: `yarn install`
   - Start Command: `node server.js`
   - Add Environment Variables (MONGODB_URI, JWT_SECRET, PORT)

## Using Blueprint (Auto-deploy)

1. Click "New" → "Blueprint"
2. Connect repository: `https://github.com/SUDHAKARJ08/bugtrackingapp.git`
3. Render will auto-detect `render.yaml` and create both services
4. Add environment variables in the dashboard

