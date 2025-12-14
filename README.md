# VPN-Workers

> Open-source VPN control plane on Cloudflare Workers + D1

**Status:** 🚧 Building in public - [Read the article](https://dev.to/YOUR_USERNAME/ARTICLE_SLUG)

## What is this?

A serverless VPN management platform that eliminates the need for PostgreSQL, Redis, and control plane servers.

- **Control Plane:** Cloudflare Workers + D1 (serverless SQLite)
- **VPN Servers:** WireGuard (lightweight daemon)
- **Dashboard:** Next.js + Tailwind

## Why?

Traditional VPN solutions require managing databases and servers just for user management and config generation. VPN-Workers runs the entire control plane on Cloudflare's edge network.

**Key benefits:**
- 💰 $11/month vs $70+ for traditional stacks
- 🌍 Global edge performance (300+ locations)
- 🔧 Zero server management
- 📦 Open source (MIT licensed)
- 🚀 Built for teams and businesses

## Architecture
```
┌─────────────────────────────────────────┐
│   Cloudflare Workers (Control Plane)    │
│   - Auth, configs, billing              │
│   - D1 serverless SQLite                │
└─────────────────────────────────────────┘
              ↓ WebSocket ↑
┌─────────────────────────────────────────┐
│   WireGuard Servers (VPS)               │
│   - Minimal Go/Rust daemon              │
│   - Standard WireGuard                  │
└─────────────────────────────────────────┘
              ↓ VPN Tunnel ↑
┌─────────────────────────────────────────┐
│   Clients (Standard WireGuard Apps)     │
└─────────────────────────────────────────┘
```

## Project Status

**Week 1** (Starting Dec 16, 2025):
- [ ] Workers API implementation
- [ ] D1 schema design
- [ ] Authentication flow
- [ ] Config generation logic

**Week 2-3:**
- [ ] WireGuard daemon (Go)
- [ ] WebSocket communication
- [ ] Next.js dashboard
- [ ] Deployment scripts

**Week 4+:**
- [ ] Beta release
- [ ] Documentation
- [ ] Community contributions

## Tech Stack

- **Backend:** Cloudflare Workers, Hono, D1
- **Frontend:** Next.js, Tailwind, shadcn/ui
- **VPN:** WireGuard, Go/Rust daemon
- **DevOps:** Wrangler, GitHub Actions

## Use Cases

- Remote teams needing secure infrastructure
- Nigerian fintech startups (compliance requirements)
- Multi-cloud deployments
- Self-hosted VPN management
- White-label VPN platforms

## How It Compares

| Feature | Pritunl | Tailscale | VPN-Workers |
|---------|---------|-----------|-------------|
| Open Source | ✅ | ❌ | ✅ |
| Serverless Control | ❌ | ❌ | ✅ |
| Monthly Cost | $70+ | $60+ | $11+ |
| Self-Hosted | ✅ | ⚠️ | ✅ |

## Contributing

🚧 **Not ready for contributions yet** - implementation starting Week 1.

**Want to help?**
- ⭐ Star this repo to follow progress
- 💬 Join [Discussions](../../discussions) to suggest features
- 📝 Read the [full article](https://dev.to/YOUR_USERNAME/ARTICLE_SLUG)
- 🐦 Follow [TWITTER](https://x.com/dannwaneri)

## Roadmap

- **Phase 1:** Core API + WireGuard daemon (Weeks 1-2)
- **Phase 2:** Dashboard + deployment automation (Weeks 3-4)
- **Phase 3:** Beta release + documentation (Month 2)
- **Phase 4:** Enterprise features (Month 3+)

## Building in Public

I'm documenting the entire build process:
- Weekly progress updates on DEV.to
- Architecture decisions in GitHub Discussions
- Real cost/performance metrics
- Lessons learned

**Follow along:**
- 📝 [DEV.to](https://dev.to/dannwaneri)
- 🐦 [Twitter](https://x.com/dannwaneri)
- 💬 [Discussions](../../discussions)

## License

MIT © Daniel Nwaneri

---

**⭐ Star this repo to follow the build!**
