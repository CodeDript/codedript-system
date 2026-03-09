# CodeDript System

CodeDript is a freelance platform built on blockchain technology. This repository is the **root monorepo** that ties together all sub-modules: client, server, blockchain, and infrastructure.

---

## Getting Started — Run the System in Minutes

### Prerequisites

Make sure the following are installed on your machine before proceeding:

- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/products/docker-desktop) & Docker Compose

---

### Step 1 — Clone the Repository

Clone the root repo along with all sub-modules in one command:

```bash
git clone --recursive https://github.com/CodeDript/codedript-core.git
cd codedript-core
```

> The `--recursive` flag automatically clones all sub-modules (`codedript-client`, `codedript-server`, `codedript-blockchain`, `codedript-infra`).

---

### Step 2 — Configure Environment Variables

Navigate into the infrastructure folder and set up the environment file:

```bash
cd codedript-infra
```

Copy the example file and rename it to `.env`:

Open `.env` in a text editor and replace all placeholder values with your actual credentials:

| Variable                    | Description                                           |
| --------------------------- | ----------------------------------------------------- |
| `MONGODB_URI`               | MongoDB connection string                             |
| `JWT_SECRET`                | A strong secret key for JWT signing                   |
| `SUPABASE_URL`              | Your Supabase project URL                             |
| `SUPABASE_ANON_KEY`         | Supabase anonymous key                                |
| `SUPABASE_SERVICE_ROLE_KEY` | Supabase service role key                             |
| `SUPABASE_BUCKET_NAME`      | Supabase storage bucket name (default: `Contracts`)   |
| `EMAIL_USER`                | Gmail address for sending emails                      |
| `EMAIL_PASSWORD`            | Gmail app password                                    |
| `SEPOLIA_RPC_URL`           | Sepolia testnet RPC URL (e.g. from Alchemy or Infura) |
| `PINATA_JWT`                | Pinata IPFS JWT token                                 |
| `PINATA_GATEWAY`            | Pinata gateway URL                                    |

---

### Step 3 — Pull Docker Images

Pull the latest pre-built Docker images for all services:

```bash
docker-compose pull
```

---

### Step 4 — Start the System

Start all services in detached (background) mode:

```bash
docker-compose up -d
```

---

### Step 5 — Open in Browser

Once all containers are running, open your browser and go to:

```
http://localhost:80
```

That's it — the system is up and running.

---



## Stopping the System

```bash
cd codedript-infra
docker-compose down
```

To also remove all volumes (resets database state):

```bash
docker-compose down -v
```
