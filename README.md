<!-- Header -->
<div align="center">

```
████████╗ █████╗ ███╗   ██╗ █████╗ ██╗   ██╗
╚══██╔══╝██╔══██╗████╗  ██║██╔══██╗╚██╗ ██╔╝
   ██║   ███████║██╔██╗ ██║███████║ ╚████╔╝ 
   ██║   ██╔══██║██║╚██╗██║██╔══██║  ╚██╔╝  
   ██║   ██║  ██║██║ ╚████║██║  ██║   ██║   
   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝  ╚═╝   ╚═╝  
```

### building systems that remove repetitive work and turn complex flows into simple commands.

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1000&color=6EE7B7&center=true&vCenter=true&width=600&lines=Full+Stack+Developer;Distributed+Systems+Enthusiast;Go+%2B+TypeScript+%2B+Node.js;Open+to+Backend+%2F+Full+Stack+Roles+%F0%9F%9A%80)](https://git.io/typing-svg)

<a href="https://linkedin.com/in/tanay-sachdeva-7119672b1"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
<a href="https://github.com/tanay-io"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/></a>
<a href="https://tanaysachdeva.in"><img src="https://img.shields.io/badge/Portfolio-111827?style=for-the-badge&logo=vercel&logoColor=white"/></a>
<a href="mailto:tanaysachdeva873@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/></a>

</div>

---

## `$ whoami`

```go
type Developer struct {
    Name        string
    Degree      string
    Institution string
    CGPA        float64
    Batch       int
    Focus       []string
}

var tanay = Developer{
    Name:        "Tanay Sachdeva",
    Degree:      "B.Tech – Electronics & Computer Engineering",
    Institution: "Thapar Institute of Engineering & Technology, Patiala",
    CGPA:        8.18,
    Batch:       2027,
    Focus:       []string{
        "Distributed Systems",
        "Backend Infrastructure",
        "API Design",
        "Full Stack Engineering",
    },
}
```

> JEE Mains 2023 — **99.02 Percentile** (Mathematics)

---

## `$ ls -la projects/`

<details>
<summary><b>⚡ RateShield — Distributed Rate Limiting Service</b> &nbsp;<code>Go · TypeScript · Redis · Lua · Docker</code></summary>

<br/>

> A production-grade rate limiting service with a typed SDK — built because naive Redis implementations break badly under concurrency.

**The problem I found:**

Running load tests against a standard multi-command Redis implementation, I watched it allow **250 requests through a strict limit of 10**. Classic race condition. No atomicity guarantee across commands under concurrent load.

**What I did:**

- Migrated critical paths to **atomic Lua scripts** executed inside Redis — enforced exactly **10 requests**, no exceptions
- Eliminated two side effects in the process: ZADD memory leaks and redundant EXPIRE flooding  
- Built **real-time observability** via Redis Pub/Sub + WebSockets, including fixing CORS constraints that break production WS deployments
- Shipped a **TypeScript SDK** (`rateshield-sdk` on NPM) with typed request/response models and configurable retry/timeout

**Numbers:**

| Algorithm | Throughput | Connections |
|-----------|-----------|-------------|
| Fixed Window | ~16k req/s | 100 concurrent |
| Sliding Window | ~8.5k req/s | 100 concurrent |
| Token Bucket | ~12k req/s | 100 concurrent |

[![GitHub](https://img.shields.io/badge/Repo-181717?style=flat-square&logo=github)](https://github.com/tanay-io/RateSheild)
[![Live](https://img.shields.io/badge/Live-00C7B7?style=flat-square&logo=vercel)](https://ratesheild.tanaysachdeva.in)

</details>

---

<details>
<summary><b>🔁 ZapRun — Governed Runtime for Internal Company Actions</b> &nbsp;<code>TypeScript · Node.js · Kafka · PostgreSQL · Prisma</code></summary>

<br/>

> **Not a Zapier clone.** ZapRun is a governed runtime that lets companies expose their internal APIs as approved, auditable business actions — then orchestrate them reliably.

The problem: companies have internal APIs (identity systems, HRIS, ticketing, device management) and no safe, auditable way to orchestrate them. ZapRun fixes that.

**Core Engine:**
- **Durable Outbox Pattern** — every job survives crashes; no lost work
- **Kafka-backed distributed workers** with atomic lease-based job claiming (60s leases, atomic `updateMany`)
- **Versioned workflow snapshots** — runs are always pinned to a frozen version; live edits never affect in-flight executions
- **Step-level state machines** with retries (max 3), replay, and delayed execution (`system.wait` + timer worker)
- **AJV schema validation** — runs at save-time AND post-interpolation at execution time; the engine fails safely instead of executing malformed configs

**Auth & Integrations:**
- Full **OAuth2 + PKCE** flow with AES-256-GCM encrypted token storage and automatic refresh before expiry
- Live integrations: **Notion, Slack, GitHub, Stripe, Gmail**
- Structured logging (Pino), CORS handling, graceful shutdown

**CLI (`zap` command):**
```bash
zap auth login          # OAuth login
zap create              # Draft a new workflow
zap test <zapId>        # Trigger a test run
zap logs --verbose      # Live step-level logs
zap replay <runId>      # Replay a past run
```

**The vision:** Add governance (policy enforcement, approval gates, environment scoping) so the engine can safely handle sensitive internal actions — then an AI layer strictly bounded by those policies.

[![GitHub](https://img.shields.io/badge/Repo-181717?style=flat-square&logo=github)](https://github.com/tanay-io/ZapRun)

</details>

---

## `$ cat experience.log`

```
[Aug 2025 – Feb 2026]  Full Stack Developer Intern @ Convivity Technologies (Remote, Delaware USA)
                       ↳ Real-time calendar scheduling backend · Node.js + Hono on Cloudflare Workers
                       ↳ RESTful APIs with JWT + OAuth 2.0 · Modular backend architecture

[Jul 2025 – Aug 2025]  Full Stack Developer Intern (Project Based) @ VetikalLabs (Remote, Bangalore)
                       ↳ Full-stack Job Summarizer · Next.js + Node.js + AWS S3
                       ↳ Structured logging + unit testing for production-grade deployment

[2024]                 Open Source Contributor @ GirlScript Summer of Code (GSSoC)
                       ↳ Shipped fixes and features across full-stack repos
```

---

## `$ cat skills.json`

```json
{
  "languages":   ["Go", "TypeScript", "JavaScript", "C++"],
  "frameworks":  ["Node.js", "Express.js", "Hono", "Next.js", "React"],
  "databases":   ["PostgreSQL", "MongoDB", "Redis"],
  "messaging":   ["Apache Kafka"],
  "tools":       ["Docker", "Git", "Linux", "AWS S3", "Prisma ORM", "Postman"],
  "concepts":    [
    "Distributed Systems",
    "Event-Driven Architecture",
    "Transactional Outbox Pattern",
    "OAuth 2.0 + PKCE",
    "JWT Authentication",
    "REST APIs",
    "Rate Limiting Algorithms"
  ]
}
```

---

## `$ cat achievements.txt`

```
✓  JEE Mains 2023     → 99.02 Percentile (Mathematics)
✓  LeetCode           → 114+ problems solved
✓  CodeChef           → Active (140+ problems across platforms)
✓  SIH 2024           → Qualified Internal Round (top among 500+ participants)
✓  GSSoC 2024         → Completed as open-source contributor
```

---

## `$ top` — What I'm working on right now

```
PID   PROCESS                          CPU    STATUS
001   ZapRun MVP                       ████░  active — building governance layer
002   DSA prep (placements 2026)       ███░░  active — daily LeetCode
003   Going deeper into Go             ██░░░  ongoing
004   Distributed systems reading      █░░░░  ongoing
```

---

<div align="center">

**`> open to backend / full stack roles and internships`**

*Patiala, Punjab → anywhere*

</div>
