# MyPreppr Deployment Guide

This guide covers multiple ways to deploy your MyPreppr website to various hosting platforms.

## Quick Deploy Options

### 1. Vercel (Recommended for Full-Stack)

**Why Vercel?**
- Perfect for React + Node.js apps
- Automatic deployments from GitHub
- Built-in environment variable management
- Free tier available

**Steps:**
1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com) and sign up
3. Click "New Project" and import your GitHub repository
4. Vercel will automatically detect the configuration
5. Add environment variables in the Vercel dashboard:
   - `SENDGRID_API_KEY` (optional)
   - `NOTIFICATION_EMAIL` (optional)
   - `FROM_EMAIL` (optional)
6. Deploy!

**Custom Domain:** Add your domain in Vercel project settings.

### 2. Netlify (Great for Static Sites)

**Steps:**
1. Build your project locally: `npm run build`
2. Go to [netlify.com](https://netlify.com) and sign up
3. Drag and drop the `dist/public` folder to Netlify
4. For continuous deployment, connect your GitHub repository
5. Add environment variables in Netlify dashboard

### 3. Railway (Simple Full-Stack Hosting)

**Steps:**
1. Go to [railway.app](https://railway.app) and sign up
2. Create new project from GitHub repository
3. Railway will automatically detect Node.js and deploy
4. Add environment variables in Railway dashboard
5. Your app will be live at a railway.app subdomain

### 4. Render (Another Great Option)

**Steps:**
1. Go to [render.com](https://render.com) and sign up
2. Create new "Web Service" from GitHub
3. Set build command: `npm run build`
4. Set start command: `npm start`
5. Add environment variables
6. Deploy!

## Environment Variables Setup

For any platform, you'll need these environment variables:

### Required for Email Notifications:
- `SENDGRID_API_KEY` - Your SendGrid API key
- `NOTIFICATION_EMAIL` - Email where you'll receive form submissions
- `FROM_EMAIL` - Email address for sending notifications

### Optional:
- `DATABASE_URL` - PostgreSQL connection string (uses in-memory storage if not provided)
- `NODE_ENV` - Set to "production" for production deployment

## GitHub Setup

1. **Create a new repository** on GitHub
2. **Push your code:**
```bash
git init
git add .
git commit -m "Initial commit: MyPreppr website"
git branch -M main
git remote add origin https://github.com/yourusername/mypreppr.git
git push -u origin main
```

## Local Development

To run locally:
```bash
npm install
npm run dev
```

Visit http://localhost:5000

## Production Build

To build for production:
```bash
npm run build
npm start
```

## Domain Setup

After deploying, you can add a custom domain:

1. **Buy a domain** (GoDaddy, Namecheap, etc.)
2. **Add domain** in your hosting platform dashboard
3. **Update DNS records** to point to your hosting platform
4. **SSL certificate** will be automatically provided

## SendGrid Email Setup

1. Create account at [sendgrid.com](https://sendgrid.com)
2. Verify your sender email address
3. Create an API key in SendGrid dashboard
4. Add the API key to your hosting platform's environment variables
5. Test email functionality through your contact form

## Troubleshooting

**Common Issues:**

1. **Build fails:** Check if all dependencies are in `package.json`
2. **Email not working:** Verify SendGrid API key and sender verification
3. **Forms not submitting:** Check network requests in browser dev tools
4. **Site not loading:** Verify build output and start command

**Getting Help:**
- Check hosting platform documentation
- Use browser developer tools to debug
- Review application logs in hosting dashboard

## Cost Estimates

| Platform | Free Tier | Paid Plans |
|----------|-----------|------------|
| Vercel | Yes (hobby projects) | $20+/month |
| Netlify | Yes (100GB bandwidth) | $19+/month |
| Railway | $5/month | $5+/month |
| Render | Yes (limited) | $7+/month |

**SendGrid:** Free tier includes 100 emails/day, perfect for contact forms.

## Next Steps

1. Choose your hosting platform
2. Push code to GitHub
3. Deploy following the guide above
4. Set up your custom domain
5. Configure email notifications
6. Test all functionality
7. Go live!

Your MyPreppr website is now ready for the world! 🚀