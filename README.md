# Content Delivery Network (CDN)

A content delivery network (CDN) is a geographically distributed group of servers that work together to provide fast delivery of internet content. Generally, static files such as HTML/CSS/JS, photos, and videos are served from CDN.

![cdn-map](https://raw.githubusercontent.com/karanpratapsingh/portfolio/master/public/static/courses/system-design/chapter-I/content-delivery-network/cdn-map.png)

## Why use a CDN?

Content Delivery Network (CDN) increases content availability and redundancy while reducing bandwidth costs and improving security. Serving content from CDNs can significantly improve performance as users receive content from data centers close to them and our servers do not have to serve requests that the CDN fulfills.

## How does a CDN work?

![cdn](https://raw.githubusercontent.com/karanpratapsingh/portfolio/master/public/static/courses/system-design/chapter-I/content-delivery-network/cdn.png)

In a CDN, the origin server contains the original versions of the content while the edge servers are numerous and distributed across various locations around the world.

To minimize the distance between the visitors and the website's server, a CDN stores a cached version of its content in multiple geographical locations known as edge locations. Each edge location contains several caching servers responsible for content delivery to visitors within its proximity.

Once the static assets are cached on all the CDN servers for a particular location, all subsequent website visitor requests for static assets will be delivered from these edge servers instead of the origin, thus reducing the origin load and improving scalability.

For example, when someone in the UK requests our website which might be hosted in the USA, they will be served from the closest edge location such as the London edge location. This is much quicker than having the visitor make a complete request to the origin server which will increase the latency.

## Types

CDNs are generally divided into two types:

### Push CDNs

Push CDNs receive new content whenever changes occur on the server. We take full responsibility for providing content, uploading directly to the CDN, and rewriting URLs to point to the CDN. We can configure when content expires and when it is updated. Content is uploaded only when it is new or changed, minimizing traffic, but maximizing storage.

Sites with a small amount of traffic or sites with content that isn't often updated work well with push CDNs. Content is placed on the CDNs once, instead of being re-pulled at regular intervals.

### Pull CDNs

In a Pull CDN situation, the cache is updated based on request. When the client sends a request that requires static assets to be fetched from the CDN if the CDN doesn't have it, then it will fetch the newly updated assets from the origin server and populate its cache with this new asset, and then send this new cached asset to the user.

Contrary to the Push CDN, this requires less maintenance because cache updates on CDN nodes are performed based on requests from the client to the origin server. Sites with heavy traffic work well with pull CDNs, as traffic is spread out more evenly with only recently-requested content remaining on the CDN.

## Disadvantages

As we all know good things come with extra costs, so let's discuss some disadvantages of CDNs:

- **Extra charges**: It can be expensive to use a CDN, especially for high-traffic services.
- **Restrictions**: Some organizations and countries have blocked the domains or IP addresses of popular CDNs.
- **Location**: If most of our audience is located in a country where the CDN has no servers, the data on our website may have to travel further than without using any CDN.

## Examples

Here are some widely used CDNs:

- [Amazon CloudFront](https://aws.amazon.com/cloudfront)
- [Google Cloud CDN](https://cloud.google.com/cdn)
- [Cloudflare CDN](https://www.cloudflare.com/cdn)
- [Fastly](https://www.fastly.com/products/cdn)


# How a CDN Works

A Content Delivery Network (CDN) enhances the speed and efficiency of content delivery over the internet. It works by:

1. **Distributing Servers Globally**  
   Placing multiple servers at different geographic locations.
   
2. **Redirecting User Requests**  
   When a user requests content (like a web page or image), the request is redirected to the nearest server.
   
3. **Delivering Cached Content**  
   The closest server responds with the cached content, reducing the data delivery time.
   
4. **Fetching and Storing New Content**  
   If the content isn't on the nearest server, it's retrieved from the origin server and cached for future requests.

# Applications of a CDN

1. **Web Content Delivery**  
   Speeding up the loading of web pages by caching HTML files, stylesheets, JavaScript, and images.
   
2. **Video Streaming**  
   Reducing buffering and improving the quality of video streaming services.
   
3. **Software Distribution**  
   Facilitating faster downloads of software, updates, and patches.
   
4. **E-commerce Platforms**  
   Enhancing the performance and user experience of online shopping sites, especially during high traffic periods.
   
5. **Online Gaming**  
   Reducing latency and improving the speed of game content delivery for a better gaming experience.
   
6. **Media and Advertising**  
   Efficient delivery of media content and advertisements to various geographical locations.
# How Caching Works in a CDN

1. **Initial Content Fetch**  
   Content is initially retrieved from the origin server upon the first request.
   
2. **Caching on Edge Servers**  
   This content is cached on CDN's edge servers, located closer to users.
   
3. **Serving Cached Content**  
   Subsequent user requests are fulfilled from the nearest edge server's cache, reducing load times.
   
4. **Time-to-Live (TTL)**  
   Cached content has a set TTL, determining how long it's stored before being refreshed from the origin server.
   
5. **Cache Invalidation**  
   Content can be manually removed or updated in the cache as needed.
   
6. **Optimization**  
   The CDN may optimize content for faster delivery, like compressing files.

# Q6. What Does TTL Mean?

TTL, or "Time to Live," is a setting that determines how long a piece of information remains valid or stored.

1. **In Networking**  
   It refers to the lifespan of data packets, decreasing with each hop in the network until they are discarded.
   
2. **In DNS Systems**  
   It dictates how long DNS records are cached before a fresh query is made.
   
3. **In Caching Systems (CDNs)**  
   It specifies how long content stays in the cache before being refreshed or removed.
   
Essentially, TTL helps balance data freshness with resource usage.

# Q7. What Does Cache Hit Ratio Mean?

Cache hit ratio refers to the percentage of requested data that is served from the cache, rather than directly from the original data source. It's a measure of the effectiveness of the cache system. 

- **Higher Ratios** indicate more efficient caching, leading to faster data retrieval and reduced load on the primary data source.

---

# Q8. What is Cache Invalidation?

Cache invalidation is the process of removing or marking cached data as outdated. This ensures that users don't receive stale or incorrect information when the original data has changed. 

- In distributed systems, invalidation can be challenging as all cache locations need to be updated or cleared simultaneously.

---

# Q9. What are Edge Servers?

Edge servers are computing nodes located close to end-users. They are designed to deliver content and services with reduced latency and improved performance by processing data closer to where it is generated or consumed.

- **Commonly Used In** distributed networks and content delivery systems.

---

# Q10. Popular CDN Providers

- **Akamai Technologies**: Extensive network, advanced security services.
- **Cloudflare**: User-friendly, integrated security services, strong web security focus.
- **Amazon CloudFront**: Seamless integration with AWS services.
- **Fastly**: High-performance edge computing, real-time updates, streaming support.
- **KeyCDN**: Cost-effective, pay-as-you-go pricing, suits small to medium businesses.
- **MaxCDN (StackPath)**: Ease of use, comprehensive web services suite.
- **CDN77**: Transparent pricing, strong data security, high bandwidth.
- **Microsoft Azure CDN**: Integration with Azure services, tailored for Microsoft applications.
- **Google Cloud CDN**: Integration with Google Cloud, advanced analytics, machine learning features.
- **Limelight Networks**: Specializes in video and media content delivery, robust content management tools.

---

# Q11. Measuring CDN Performance

1. **Latency**: Time taken for a request to reach the CDN and for the response to reach the user.
2. **Content Load Time**: Time it takes for content to fully load in a user's browser.
3. **Availability/Uptime**: Percentage of time the CDN is operational without outages.
4. **Cache Hit Ratio**: Percentage of requests served from the CDN's cache.
5. **Throughput**: Amount of data transferred over time, indicating the CDN's capacity.
6. **Error Rate**: Number of failed requests or errors during content delivery.
7. **Geographical Performance**: Performance consistency across different geographic locations.
8. **Bandwidth Usage**: Monitoring traffic patterns and peak usage times.
9. **Page Load Time**: Overall time for a web page to fully load on a user's device.
10. **Time to First Byte (TTFB)**: Time from the user's request to the first byte received by the browser.
11. **End User Experience Monitoring**: Real or simulated user interactions to gauge user experience.
12. **Security Performance**: Effectiveness in protecting against attacks and handling secure connections.

---

# Q12. How DNS Plays a Role in CDN Functionality

DNS (Domain Name System) plays a key role in CDN functionality by directing user requests to the optimal server, enhancing content delivery:

1. **Domain Name Resolution**: The browser contacts a DNS server to translate a domain name into an IP address.
2. **CDN Integration**: Websites using a CDN have their DNS configurations point to the CDN's DNS servers.
3. **Geolocation and Server Selection**: The CDN's DNS server determines the user's location and selects the nearest or most suitable edge server.
4. **Routing User Requests**: The CDN DNS responds with the IP address of the chosen edge server, ensuring the user connects to the optimal server.
5. **Load Balancing**: The CDN DNS evenly distributes traffic to prevent overloading servers.
6. **Improved Performance**: By routing users to the closest or best-performing server, DNS reduces latency.
7. **Handling Traffic Spikes and Failover**: The CDN can redistribute traffic during high traffic times and reroute requests in case of server outages, ensuring availability.

---

# Q13. Architecture of a Typical CDN

The architecture of a typical Content Delivery Network (CDN) includes several key components designed to optimize content delivery:

1. **Origin Server**: The primary source of the website's content.
2. **Edge Servers (Nodes)**: Globally distributed to cache and serve content closer to users.
3. **Points of Presence (PoPs)**: Clusters of edge servers ensuring local users receive content quickly.
4. **DNS Resolution**: Directs user requests to the nearest or most optimal edge server.
5. **Load Balancers**: Distribute user requests evenly among edge servers to prevent overload.
6. **Caching Mechanisms**: Temporarily store content on edge servers, reducing load on the origin server.
7. **Content Replication**: Duplicates content from the origin to edge servers.
8. **Network Layer**: Connects edge servers, PoPs, and the origin server, optimizing data routing.
9. **Control Layer**: Manages content distribution and delivery, including security and analytics.
10. **Security Features**: Protects against cyber threats with DDoS protection and SSL/TLS encryption.
11. **APIs and Administration Tools**: Allow management and configuration of CDN settings.
