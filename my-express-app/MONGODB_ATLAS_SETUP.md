# MongoDB Atlas Setup Guide

## Steps to Set Up MongoDB Atlas:

1. **Create a MongoDB Atlas Account**
   - Go to https://www.mongodb.com/cloud/atlas
   - Sign up for a free account

2. **Create a Cluster**
   - Click "Create" or "Build a Database"
   - Choose the FREE tier (M0 Sandbox)
   - Select a cloud provider and region (choose closest to you)
   - Click "Create Cluster"

3. **Create Database User**
   - Go to "Database Access" in the left sidebar
   - Click "Add New Database User"
   - Choose "Password" authentication
   - Create a username and password (save these!)
   - Set user privileges to "Atlas admin" or "Read and write to any database"
   - Click "Add User"

4. **Configure Network Access**
   - Go to "Network Access" in the left sidebar
   - Click "Add IP Address"
   - Click "Allow Access from Anywhere" (for development) or add your IP address
   - Click "Confirm"

5. **Get Your Connection String**
   - Go to "Database" in the left sidebar
   - Click "Connect" on your cluster
   - Choose "Connect your application"
   - Copy the connection string (it looks like: `mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/?retryWrites=true&w=majority`)

6. **Update Your .env File**
   - Create a `.env` file in the `my-express-app` directory
   - Add your connection string:
   ```
   MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/todoapp?retryWrites=true&w=majority
   PORT=5000
   FRONTEND_URL=http://localhost:3000
   ```
   - Replace `<username>` and `<password>` with your database user credentials
   - Replace `cluster0.xxxxx` with your actual cluster address
   - The `/todoapp` part is the database name (you can change it)

## Example .env file:

```
MONGODB_URI=mongodb+srv://myuser:mypassword@cluster0.abc123.mongodb.net/todoapp?retryWrites=true&w=majority
PORT=5000
FRONTEND_URL=http://localhost:3000
```

## Testing the Connection

After setting up your `.env` file, restart your server:
```bash
npm start
# or
npm run dev
```

You should see: `MongoDB Connected: cluster0.xxxxx.mongodb.net`

