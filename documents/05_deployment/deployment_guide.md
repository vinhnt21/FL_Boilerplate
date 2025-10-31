# Deployment Guide

> Status: 🔒 LOCKED
> Version: v1.0
> Locked by: [Your Name]
> Locked at: YYYY-MM-DD
> Note: Step-by-step deployment instructions

## Environment Setup

### Prerequisites
- Docker installed
- Node.js 18+ installed
- Database access credentials
- SSL certificates
- Domain configuration

### Environment Variables
```bash
# Database
DATABASE_URL=postgresql://user:password@host:port/database
DB_HOST=localhost
DB_PORT=5432
DB_NAME=production_db
DB_USER=db_user
DB_PASSWORD=db_password

# Application
NODE_ENV=production
PORT=3000
JWT_SECRET=your_jwt_secret
API_URL=https://api.yourdomain.com

# External Services
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password
```

## Deployment Steps

### 1. Backend Deployment
```bash
# Build Docker image
docker build -t your-app-backend .

# Run database migrations
docker run --rm your-app-backend npm run migrate

# Deploy to production
docker run -d --name your-app-backend \
  -p 3000:3000 \
  --env-file .env.production \
  your-app-backend
```

### 2. Frontend Deployment
```bash
# Build production bundle
npm run build

# Deploy to web server
rsync -avz dist/ user@server:/var/www/html/
```

### 3. Database Setup
```sql
-- Create production database
CREATE DATABASE production_db;
CREATE USER db_user WITH PASSWORD 'db_password';
GRANT ALL PRIVILEGES ON DATABASE production_db TO db_user;

-- Run migrations
\i migrations/001_initial_schema.sql
\i migrations/002_add_users_table.sql
```

### 4. Nginx Configuration
```nginx
server {
    listen 80;
    server_name yourdomain.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl;
    server_name yourdomain.com;
    
    ssl_certificate /path/to/certificate.crt;
    ssl_certificate_key /path/to/private.key;
    
    location / {
        root /var/www/html;
        try_files $uri $uri/ /index.html;
    }
    
    location /api {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

## Monitoring Setup

### Health Checks
- **Backend:** `GET /api/health`
- **Database:** Connection test
- **Frontend:** Static file serving

### Log Monitoring
```bash
# View application logs
docker logs -f your-app-backend

# View nginx logs
tail -f /var/log/nginx/access.log
tail -f /var/log/nginx/error.log
```

### Performance Monitoring
- Set up uptime monitoring
- Configure error tracking
- Monitor database performance
- Track API response times

## Troubleshooting

### Common Issues
1. **Database Connection Failed**
   - Check credentials
   - Verify network connectivity
   - Check firewall rules

2. **SSL Certificate Issues**
   - Verify certificate validity
   - Check private key permissions
   - Restart nginx

3. **Application Won't Start**
   - Check environment variables
   - Verify port availability
   - Check Docker logs

### Rollback Procedure
```bash
# Stop current version
docker stop your-app-backend

# Start previous version
docker run -d --name your-app-backend-rollback \
  -p 3000:3000 \
  --env-file .env.production \
  your-app-backend:previous
```
