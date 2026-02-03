## Performance Checklist

### Database
- No N+1 queries (batch/join/eager load where possible)
- Fetch only required columns/fields
- Indexes exist for frequent queries
- Pagination for large result sets
- Connection pooling configured appropriately

### Resources
- Promises/async operations awaited and errors handled
- No runaway loops or excessive allocations
- Large payloads avoided or streamed
- Files and connections properly closed/cleaned up
- Memory leaks identified (event listeners, subscriptions, caches)

### Concurrency
- Race conditions identified and handled
- Deadlock potential assessed
- Resource cleanup on cancellation/timeout
- Thread safety where applicable

### Caching
- Appropriate caching strategy (memory, distributed, HTTP)
- Cache invalidation handled correctly
- Cache key collisions avoided

### General
- Algorithmic complexity reasonable for data size
- Hot paths optimized
- Lazy loading for expensive operations
- Logging not excessive in production
