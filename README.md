# GSA Private Access Sizing Planner — Getting Started

> **No installation required.** Open `index.html` in any modern browser and start sizing.
>
> Works completely offline — no server, no internet, no account needed.

---

## What Does This Tool Do?

Answers one practical question:

> *"How many Entra Private Access connector servers do I need — and how big should they be?"*

Describe your users and their applications (how many users, what protocols they use, how much data flows). The tool calculates your actual bandwidth, CPU, and memory demand, then tells you how many servers you need.

---

## Quick Start

1. Open **`index.html`** to choose a planning mode
2. Select **Single-Site** for one location, or **Multi-Site** for enterprise multi-region planning
3. Enter your concurrent user count and select a protocol profile (or blend multiple)
4. Review the results — server count, limiting factor, and the three provisioning scenarios

> Chrome 80+, Firefox 75+, Safari 13+, and Edge 80+ are supported.

---

## The Three Provisioning Scenarios

Your "actual demand" is the raw minimum. In production you should never run at 100%:

- Traffic is **bursty** — logins, batch jobs, and large file syncs spike suddenly
- You need **zero-downtime maintenance** — rolling restarts require spare headroom
- You want **graceful degradation** — one misbehaving app shouldn't take everything down

The tool calculates three scenarios based on target utilization:

| Scenario | Utilization Cap | Headroom | Best For |
|----------|----------------|----------|----------|
| **Conservative** | 60% | 40% | Critical services, unpredictable workloads |
| **Balanced** | 70% | 30% | Standard enterprise deployments ← recommended |
| **Efficient** | 80% | 20% | Stable workloads with good monitoring |

> **Start with Balanced (70%)** for most deployments. The **Limiting Factor** column tells you whether to add CPU, RAM, or faster NICs to reduce the count.

---

## Tips for Accurate Sizing

1. **Use concurrent users, not total users.** If 10,000 employees exist but only 3,000 are ever online simultaneously, enter 3,000.

2. **Choose the right deployment type.** Cloud VMs carry virtualization overhead — they need more total resources than bare metal to deliver the same effective capacity.

3. **Blend protocols for mixed app portfolios.** If users access web apps *and* file shares, use protocol blending rather than picking a single protocol. Different protocols generate very different bandwidth profiles.

4. **Add 1 server for fault tolerance.** The tool shows the minimum count. In production, always run N+1 so that losing one server doesn't push you over your capacity target.

5. **Use Azure VM Recommendations** (Single-Site) for cost-optimized VM suggestions based on your Balanced scenario requirements.

---

## Exporting Results

| Format | How | Contains |
|--------|-----|---------|
| **PDF** | Click "Export PDF" | Actual demand, all 3 scenarios, server configuration |
| **JSON** | Click "Export JSON" (Multi-Site) | Full configuration for archiving or re-importing |

---

*For full documentation, visit the [project repository](https://github.com/FranckhDev/GSA-Private-Access-Sizing-Planner).*
