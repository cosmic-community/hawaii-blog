# Hawaii Surf Blog

![Hawaii Surf Blog](https://imgix.cosmicjs.com/749a6fb0-7078-11f0-a051-23c10f41277a-photo-1502933691298-84fc14542831-1754232308122.jpg?w=1200&h=300&fit=crop&auto=format,compress)

A modern, responsive surf blog built with Next.js 15 and powered by Cosmic. Features surf reports, spot guides, gear reviews, and detailed author profiles showcasing Hawaii's legendary surf culture.

## ✨ Features

- **Dynamic Content Management** - All content powered by your existing Cosmic bucket
- **Surf-Specific Metadata** - Wave height, wind conditions, surf ratings, and spot information
- **Category System** - Color-coded categories for Surf Reports, Surf Spots, and Gear Reviews
- **Author Profiles** - Detailed author pages with photos, bios, and surfing experience
- **Responsive Design** - Optimized for all devices from desktop to mobile
- **SEO Optimized** - Proper meta tags and structured data
- **Fast Performance** - Built with Next.js 15 App Router for optimal speed
- **Image Optimization** - Automatic image optimization with imgix

## Clone this Bucket and Code Repository

Want to create your own version of this project with all the content and structure? Clone this Cosmic bucket and code repository to get started instantly:

[![Clone this Bucket and Code Repository](https://img.shields.io/badge/Clone%20this%20Bucket-29abe2?style=for-the-badge&logo=cosmic&logoColor=white)](https://app.cosmic-staging.com/projects/new?clone_bucket=688f758eb5e4a42c017a283a&clone_repository=688f91c170106502cd8408cc)

## Prompts

This application was built using the following prompts to generate the content structure and code:

### Content Model Prompt

> "Create a content model for a Hawaii surf blog with posts, authors, and categories"

### Code Generation Prompt

> Build a Next.js website that uses my existing objects in this bucket

The app has been tailored to work with your existing Cosmic content structure and includes all the features requested above.

## 🚀 Technologies

- **Next.js 15** - React framework with App Router
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first CSS framework
- **Cosmic** - Headless CMS for content management
- **Imgix** - Image optimization and delivery

## 🏗️ Getting Started

### Prerequisites

- Node.js 18+ or Bun
- A Cosmic account and bucket

### Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   bun install
   ```

3. Set up environment variables:
   ```bash
   cp .env.example .env.local
   ```

4. Add your Cosmic credentials to `.env.local`:
   ```
   COSMIC_BUCKET_SLUG=your-bucket-slug
   COSMIC_READ_KEY=your-read-key
   COSMIC_WRITE_KEY=your-write-key
   ```

5. Run the development server:
   ```bash
   bun dev
   ```

6. Open [http://localhost:3000](http://localhost:3000) in your browser

## 📚 Cosmic SDK Examples

### Fetching All Posts
```typescript
import { cosmic } from '@/lib/cosmic'

const posts = await cosmic.objects
  .find({ type: 'surf-posts' })
  .props(['id', 'title', 'slug', 'metadata'])
  .depth(1)
```

### Fetching a Single Post
```typescript
const post = await cosmic.objects
  .findOne({ type: 'surf-posts', slug: 'post-slug' })
  .depth(1)
```

### Fetching Posts by Category
```typescript
const posts = await cosmic.objects
  .find({ 
    type: 'surf-posts',
    'metadata.category': categoryId 
  })
  .depth(1)
```

## 🌐 Cosmic CMS Integration

This website is fully integrated with your Cosmic bucket structure:

- **Surf Posts** (`surf-posts`) - Blog posts with rich metadata including wave conditions, surf ratings, and spot information
- **Authors** (`authors`) - Author profiles with photos, bios, years surfing, and favorite spots  
- **Categories** (`categories`) - Content categories with custom colors for visual organization

All content is dynamically fetched from your Cosmic bucket and rendered with proper TypeScript typing for a robust development experience.

## 🚀 Deployment

### Deploy to Vercel

1. Connect your repository to Vercel
2. Add environment variables in Vercel dashboard:
   - `COSMIC_BUCKET_SLUG`
   - `COSMIC_READ_KEY`
   - `COSMIC_WRITE_KEY`
3. Deploy!

### Deploy to Netlify

1. Connect your repository to Netlify
2. Add environment variables in Netlify dashboard
3. Set build command to `bun run build`
4. Set publish directory to `.next`
5. Deploy!

For production deployment, ensure all environment variables are properly configured in your hosting platform.

<!-- README_END -->