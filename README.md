# Snow Cloud

Snow Cloud is a free and open-source file server and management system. Snow Cloud works very similarly to other cloud file providers, like iCloud, OneDrive, or Google Drive.

## Snow Cloud System Architecture

### Server

The backend server is built using [TypeScript](https://www.typescriptlang.org/docs/), [Fastify](https://www.fastify.io/docs/latest/), and [Prisma](https://www.prisma.io/docs). The source code can be found [here](https://github.com/SnowbankLabs/snow-cloud-server).

### Client

The main web client (webui) is built using [TypeScript](https://www.typescriptlang.org/docs/), [Next.js](https://nextjs.org), [React](https://reactjs.org/), and [Tailwind](https://tailwindcss.com/). The source code can be found [here](https://github.com/SnowbankLabs/snow-cloud-webui).

### Server-Client Communication

Snow Cloud user-facing clients communicate with the backend server over the Snow Cloud Server REST API.

### Authentication Mechanism

Snow Cloud uses a token-based authentication system. On login, this server return an access-token and refresh-token. The access-token only provides access to protected resources for 15 minutes. After the access-token expires, the client will attempt to fetch a new token by using the refresh-token, which has a much longer lifespan. To prevent the possibility of account compromise due to a stolen refresh-token, this system implements refresh-token rotation and automatic refresh-token reuse detection. This mechanism is outlined in [this blog post](https://auth0.com/blog/refresh-tokens-what-are-they-and-when-to-use-them/) by the team at Auth0.

---

# Snow Cloud Info

### Repositories

-   [`snow-cloud`](https://github.com/SnowbankLabs/snow-cloud) : Contains an overview of the Snow Cloud system.
-   [`snow-cloud-server`](https://github.com/SnowbankLabs/snow-cloud-server) : Contains source code for the Snow Cloud backend server.
-   [`snow-cloud-webui`](https://github.com/SnowbankLabs/snow-cloud-webui) : Contains source code for the Snow Cloud web client.

## Legal

Snow Cloud is developed and maintained by Snowbank Labs. Snow Cloud is distributed under the AGPL v3 license.
