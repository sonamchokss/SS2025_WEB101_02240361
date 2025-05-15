# Practical 5: Infinite Scroll with TanStack Query

## Project Overview
Implemented cursor-based infinite scroll in the TikTok clone using:
- TanStack Query (`useInfiniteQuery`)
- Intersection Observer API
- Next.js App Router
- Custom backend pagination

## Key Features
**Infinite Scroll**
- Smooth content loading on scroll
- Cursor-based pagination
- No duplicate or missing items

**Performance Optimizations**
- Request deduplication
- Smart cache management
- Background pre-fetching

**Intersection Detection**
- Efficient scroll monitoring
- Low-performance impact
- Mobile-friendly

## Setup Instructions

### Backend Requirements
1. Update video controllers:
```javascript
{
  videos: [...],
  nextCursor: "last_video_id",
  hasNextPage: true
}
```

### Frontend Installation
```bash
npm install @tanstack/react-query @tanstack/react-query-devtools
```

### Configuration
1. Wrap app with QueryClientProvider in layout.js
2. Update video service methods:

```javascript
const getVideos = async ({ pageParam = null }) => {
  const params = new URLSearchParams({ limit: 10 });
  if (pageParam) params.set('cursor', pageParam);
  return api.get(`/videos?${params}`);
};
```

## Implementation Guide
### Backend Changes
1. Modified video controllers to use:
- Cursor instead of page numbers
- Prisma's cursor and skip methods
- "n+1 pattern" for hasNextPage

### Frontend Components
1. VideoFeed.jsx:
```jsx
const {
  data,
  fetchNextPage,
  hasNextPage,
  isFetchingNextPage
} = useInfiniteQuery({
  queryKey: ['videos'],
  queryFn: getVideos,
  getNextPageParam: (lastPage) => 
    lastPage.hasNextPage ? lastPage.nextCursor : undefined
});
```

2. useIntersectionObserver.js:
```javascript
const observerRef = useIntersectionObserver((entry) => {
  if (entry.isIntersecting && hasNextPage) {
    fetchNextPage();
  }
});
```

### Demo Instructions
1. Scroll to bottom of feed
2. Observe loading spinner
3. New videos automatically appear
4. Try with different network speeds (DevTools > Network throttling)
