# OpenCloud

OpenCloud is a free and open-source file server and management system. OpenCloud works similarly to other cloud file providers, like iCloud, OneDrive, or Google Drive.

## OpenCloud System Architecture

### Server

The backend server is built using [TypeScript](https://www.typescriptlang.org/docs/), [Fastify](https://www.fastify.io/docs/latest/), and [Prisma](https://www.prisma.io/docs). The source code can be found [here](https://github.com/SnowbankLabs/OpenCloud-Server).

### Client

The main web client (webui) is built using [TypeScript](https://www.typescriptlang.org/docs/), [Next.js](https://nextjs.org), [React](https://reactjs.org/), and [Tailwind](https://tailwindcss.com/). The source code can be found [here](https://github.com/SnowbankLabs/OpenCloud-WebUI).

### Server-Client Communication

OpenCloud user-facing clients communicate with the backend server over the Snow Cloud Server REST API.

### Authentication Mechanism

OpenCloud uses a token-based authentication system. On login, this server return an access-token and refresh-token. The access-token only provides access to protected resources for 15 minutes. After the access-token expires, the client will attempt to fetch a new token by using the refresh-token, which has a much longer lifespan. To prevent the possibility of account compromise due to a stolen refresh-token, this system implements refresh-token rotation and automatic refresh-token reuse detection. This mechanism is outlined in [this blog post](https://auth0.com/blog/refresh-tokens-what-are-they-and-when-to-use-them/) by the team at Auth0.

---

# OpenCloud Info

### Repositories

-   [`OpenCloud`](https://github.com/SnowbankLabs/OpenCloud) : Contains an overview of the Snow Cloud system.
-   [`OpenCloud-Server`](https://github.com/SnowbankLabs/OpenCloud-Server) : Contains source code for the Snow Cloud backend server.
-   [`OpenCloud-WebUI`](https://github.com/SnowbankLabs/OpenCloud-WebUI) : Contains source code for the Snow Cloud web client.

## Legal

OpenCloud is developed and maintained by Snowbank Labs. OpenCloud is distributed under the AGPL v3 license.
