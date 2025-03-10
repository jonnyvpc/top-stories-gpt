# Webflow Integration Guide

## Overview
This guide details the integration between Top Stories GPT and Webflow CMS, ensuring seamless content publishing while respecting Webflow's interface limitations.

## CMS Collection Structure

### Base Fields
- **Name** (Plain text, Required)
  - Main title of the article
  - Used for URL slug generation
- **Slug** (Plain text, Required)
  - Auto-generated from Name
  - Format: `webflow.com/news/post`

### Custom Fields

1. **Content Control**
   - `exclusive-onoff` (Boolean)
     - Toggle for exclusive content
     - Controls content visibility

2. **Article Structure**
   - `attention-grabber` (Plain text, Required)
     - Hook text above main title
   - `attention-title` (Plain text)
     - Secondary attention-grabbing headline
   - `post-summary` (Rich text)
     - Executive summary
     - Appears in blog post grid
   - `ad-embed` (Rich text)
     - Optional advertising content
   - `post-body` (Rich text)
     - Main article content
     - Supports rich text formatting

3. **Media Fields**
   - `main-image` (Image)
     - Primary article image
     - Recommended size: 16:9 ratio
   - `thumbnail-image` (Image)
     - Blog grid thumbnail
     - Optimized for grid display
   - `inline-gallery` (Multi-image)
     - Supporting image collection
     - Optional visual content

4. **Additional Content**
   - `post-body-2` (Rich text)
     - Second content section
   - `post-body-3` (Rich text)
     - Third content section
   - `featured` (Boolean)
     - Priority content flag
   - `order` (Number)
     - Custom sort order

## Collection Settings

### URL Structure
- Base path: `/news/post/`
- Slug format: `{post-title}`
- Full URL pattern: `www.{domain}.com/news/post/{slug}`

### Field Dependencies
1. **Required Fields**
   - Name
   - Slug
   - attention-grabber
   - post-summary
   - main-image
   - thumbnail-image

2. **Optional Fields**
   - exclusive-onoff
   - attention-title
   - ad-embed
   - inline-gallery
   - featured
   - order

## Integration Guidelines

### Content Publishing
1. **Title Structure**
   ```
   {attention-grabber}
   {Name}
   {attention-title}
   ```

2. **Body Structure**
   ```
   [Summary]
   {post-summary}

   [Main Content]
   {post-body}
   {post-body-2}
   {post-body-3}

   [Media]
   {main-image}
   {inline-gallery}
   ```

### Image Requirements
1. **Main Image**
   - Aspect ratio: 16:9
   - Min width: 1200px
   - Format: JPG/PNG

2. **Thumbnail**
   - Aspect ratio: 3:2
   - Size: 400x300px
   - Format: JPG/PNG

3. **Gallery Images**
   - Max size: 2MB per image
   - Recommended width: 800px
   - Format: JPG/PNG

## API Integration

### Authentication
```json
{
  "headers": {
    "Authorization": "Bearer {WEBFLOW_API_KEY}",
    "Content-Type": "application/json"
  }
}
```

### Create Post Example
```json
{
  "fields": {
    "name": "Article Title",
    "slug": "article-title",
    "exclusive-onoff": false,
    "attention-grabber": "MARKET INSIGHT",
    "attention-title": "Strategic Analysis",
    "post-summary": "Executive summary of the article...",
    "post-body": "Main content section...",
    "post-body-2": "Secondary content...",
    "post-body-3": "Final section...",
    "main-image": {
      "url": "https://assets.website.com/image.jpg",
      "alt": "Article main image"
    }
  }
}
```

## Best Practices

1. **Content Structure**
   - Follow WSJ/FT style guidelines
   - Maintain consistent heading hierarchy
   - Use proper rich text formatting

2. **Image Optimization**
   - Compress images before upload
   - Include descriptive alt text
   - Maintain aspect ratios

3. **SEO Optimization**
   - Utilize attention-grabber for meta titles
   - Include post-summary in meta description
   - Optimize image alt text

4. **Performance**
   - Lazy load gallery images
   - Cache API responses
   - Monitor API rate limits

## Webflow Setup Steps

1. **CMS Collection Creation**
   - Navigate to Webflow CMS panel
   - Create new collection using above structure
   - Enable API access for the collection

2. **Template Configuration**
   - Use existing site template
   - Add CMS collection list
   - Configure dynamic bindings for all fields
   - Set up responsive image handling

3. **API Integration**
   - Locate Collection ID in Webflow settings
   - Configure webhook endpoint in Make.com
   - Set up API authentication

## Content Publishing Rules

1. **Image Handling**
   - Upload images to Webflow CDN first
   - Use returned CDN URLs in content
   - Maintain 16:9 aspect ratio for main images
   - Optimize thumbnails to 400x300px

2. **Rich Text Formatting**
   - Use standard HTML tags only
   - Avoid custom CSS classes
   - Maintain consistent heading hierarchy
   - Use native Webflow components

3. **SEO Optimization**
   - Auto-generate meta descriptions
   - Configure OpenGraph tags
   - Set up canonical URLs
   - Enable sitemap inclusion

## Webhook Configuration

```json
{
  "endpoint": "https://{site-name}.webflow.io/api/v1/collections/{collection-id}/items",
  "method": "POST",
  "headers": {
    "Authorization": "Bearer {api-key}",
    "Content-Type": "application/json"
  }
}
```

## Error Handling

1. **API Rate Limits**
   - Maximum 60 requests per minute
   - Implement exponential backoff
   - Queue posts during high volume

2. **Content Validation**
   - Verify all required fields
   - Check image URLs before publishing
   - Validate HTML structure

3. **Fallback Procedures**
   - Store failed posts in backup queue
   - Send admin notifications
   - Provide manual override option
