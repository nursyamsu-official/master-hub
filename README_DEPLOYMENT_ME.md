# Deployment Guide

### Preprequisites

1. VPS: Ubuntu, CPU: 4/6, RAM: 4/6, SSD/NVMe: ..GB, Bandwidth: ..GB
2. Firewall Port: port 22 (or custom ssh port), 80, 443, 5432 (or custom postgres port), 3000, 3001, ..
3. Domain/Subdomain
4. Install: nginx, cerbot, nodejs, npm, pnpm, postgres + (custom port, remote, etc), pm2
5. Virtual host
6. SSL: cerbot, nginx
7. Git: git clone <repo-url> apps_name
8. copy .env.example to .env and set env: NEXT_PUBLIC_SITE_URL,BETTER_AUTH_SECRET, DATABASE_URL, EMAIL_FROM, RESEND_API_KEY, SENTRY_ORG, SENTRY_PROJECT, SENTRY_AUTH_TOKEN, NEXT_PUBLIC_SENTRY_DSN
9. copy ecosystem.config.js.example to ecosystem.config.js and adjust: name, cwd, port
10. execute: pnpm run deploy
11. execute: pm2 start ecosystem.config.js
12. execute: pm2 startup
13. execute: pm2 save