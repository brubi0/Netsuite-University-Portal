# NetSuite University Portal - Deployment Guide

## Live Site
**URL:** https://nup.urkuconsulting.com

## Infrastructure
| Component | Details |
|-----------|---------|
| Domain | urkuconsulting.com (Namecheap) |
| Subdomain | nup.urkuconsulting.com |
| Server | Digital Ocean Droplet (134.199.202.25) |
| Web Server | Nginx 1.24.0 |
| SSL | Let's Encrypt (auto-renews) |
| Web Root | /var/www/nup.urkuconsulting.com |

## Updating the Site

### Option 1: From Windows Terminal

```bash
# 1. Push changes to GitHub
cd "C:\Users\BXR\OneDrive\Documents\GitHub\Netsuite University Portal"
git add .
git commit -m "Your commit message"
git push

# 2. SSH into the droplet and pull changes
ssh brubio@134.199.202.25
cd /var/www/nup.urkuconsulting.com
git pull
exit
```

### Option 2: One-liner (after pushing to GitHub)

```bash
ssh brubio@134.199.202.25 "cd /var/www/nup.urkuconsulting.com && git pull"
```

## SSH Access

```bash
ssh brubio@134.199.202.25
```

SSH key location: `~/.ssh/id_ed25519`

## Nginx Configuration

Config file: `/etc/nginx/sites-available/nup.urkuconsulting.com`

### Useful Commands (run on droplet)

```bash
# Test nginx config
sudo nginx -t

# Reload nginx (after config changes)
sudo systemctl reload nginx

# Restart nginx
sudo systemctl restart nginx

# Check nginx status
sudo systemctl status nginx

# View nginx error logs
sudo tail -f /var/log/nginx/error.log

# View access logs
sudo tail -f /var/log/nginx/access.log
```

## SSL Certificate

Certificate is managed by Certbot and auto-renews. To manually renew:

```bash
sudo certbot renew
```

## Troubleshooting

### Site not loading after droplet reboot
Nginx should auto-start. If not:
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

### Permission issues with git pull
```bash
sudo chown -R brubio:www-data /var/www/nup.urkuconsulting.com
```

### Check if site files exist
```bash
ls -la /var/www/nup.urkuconsulting.com
```

---

**Created:** December 2025
