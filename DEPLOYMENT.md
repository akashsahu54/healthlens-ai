# Deployment Guide

## Quick Deploy to Vercel (Recommended)

1. Push your code to GitHub

2. Go to [vercel.com](https://vercel.com)

3. Click "Import Project"

4. Select your GitHub repository

5. Add environment variable:
   - Key: `ANTHROPIC_API_KEY`
   - Value: Your Claude API key

6. Click "Deploy"

Done! Your app will be live at `your-project.vercel.app`

## Get Gemini API Key

1. Go to [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Sign in with Google account
3. Click "Create API Key"
4. Copy and save it securely

Your key: AIzaSyBd2r0acpPSYk2IQl80b9bqAtyN3bPEuxw

## Alternative: Deploy to Netlify

```bash
npm run build
netlify deploy --prod
```

Add environment variable in Netlify dashboard.

## Local Development

```bash
npm install
npm run dev
```

Open http://localhost:3000

## Environment Variables

Required:
- `GEMINI_API_KEY` - Your Google Gemini API key

## Build Commands

- Development: `npm run dev`
- Production build: `npm run build`
- Start production: `npm start`
- Lint: `npm run lint`

## Performance Optimization

- Images are optimized automatically by Next.js
- API routes are serverless (auto-scaling)
- Static assets cached via CDN
- Code splitting enabled

## Monitoring

Add these services for production:
- Vercel Analytics (built-in)
- Sentry for error tracking
- PostHog for user analytics

## Security

- API key stored in environment variables
- No sensitive data in client-side code
- HTTPS enforced
- CORS configured properly

## Troubleshooting

**OCR not working?**
- Check image quality (clear, well-lit)
- Ensure text is readable
- Try different image format

**API errors?**
- Verify GEMINI_API_KEY is set
- Check API key is valid
- Review API rate limits (Gemini has generous free tier)

**Build fails?**
- Run `npm install` again
- Clear `.next` folder
- Check Node.js version (18+)
