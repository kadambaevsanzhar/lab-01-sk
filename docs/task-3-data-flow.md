Task 3 — Data flow and system interactions: Spotify



&nbsp;1. Main components

\- Client applications (Web, Mobile, Desktop)

\- API Gateway

\- Auth Service

\- Backend services (Catalog, Library, Playback)

\- Cache

\- Databases

\- Messaging / Event stream

\- Analytics and ML services

\- CDN



&nbsp;2. Synchronous data flow

1\. Client sends request to API Gateway.

2\. API Gateway validates request via Auth Service.

3\. Request is routed to the target backend service.

4\. Service reads data from cache or database.

5\. Response is returned to the client.



Used for search, playback start, playlists, and profile actions.



&nbsp;3. Asynchronous data flow

1\. Backend services emit events (plays, likes, skips).

2\. Events are published to the message broker.

3\. Data pipelines consume events.

4\. Data is stored in analytics storage.

5\. ML services use data for training and recommendations.



Used for analytics, recommendations, monitoring, and experiments.



&nbsp;4. Critical data paths

\- Playback: Client → API → Playback Service → CDN

\- Authentication: Client → API → Auth Service

\- Recommendations: Events → Data pipeline → ML → Backend



&nbsp;5. Assumptions

\- High read traffic and low latency requirements.

\- Eventual consistency is acceptable for analytics.

\- Architecture is conceptual and simplified.



