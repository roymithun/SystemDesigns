### Eviction Policy

Eviction policy is a strategy used by caching systems to determine which items should be removed or evicted from the cache when the cache reaches its capacity limit. When the cache is full and a new item needs to be added, the eviction policy determines which existing item(s) should be removed to make space for the new item.

Common eviction policies include:

- **Least Recently Used (LRU)**: Removes the least recently accessed items from the cache. This policy assumes that items accessed less recently are less likely to be accessed in the near future.

- **Least Frequently Used (LFU)**: Evicts the least frequently accessed items from the cache. This policy removes items that have been accessed the least number of times, assuming that they are less valuable or important than frequently accessed items.

- **Time To Live (TTL)**: Removes items from the cache after a specified time period, regardless of their access frequency. This policy is useful for expiring cached data that may become stale over time.

- **First-In-First-Out (FIFO)**: Evicts the oldest items that were added to the cache when the cache is full. Items are evicted in the order they were inserted into the cache, with the oldest items being removed first.

- **Random Replacement**: Selects items to evict randomly from the cache when it's full. While simple to implement, random replacement may not be as efficient as other policies in terms of cache performance and effectiveness.

- **W-TinyLFU**: Combines the benefits of both LRU and LFU by using a probabilistic data structure called TinyLFU along with a windowed approach to track access frequency. W-TinyLFU dynamically adjusts to changing access patterns and efficiently identifies items for eviction based on their likelihood of being accessed in the future.

- **Clock (Clock-Pro)**: An enhancement of the FIFO policy that uses a circular buffer with a "hand" to keep track of the last-accessed time of each item. When an item is accessed, its corresponding bit in the buffer is set to 1, and the hand moves to the next position. Eviction occurs when the hand points to an item with its bit set to 0, indicating that it hasn't been accessed since the last cycle.

The choice of eviction policy depends on factors such as the access patterns of the cached data, the importance of preserving certain items in the cache, and the performance requirements of the application.
