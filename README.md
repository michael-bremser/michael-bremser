# Michael Bremser

**Infrastructure & DevOps Engineering | Ventura, CA**

I'm 41, I don't have a CS degree, and I'm not pretending otherwise. What I have is fifteen years of operational leadership in high-end hospitality — managing systems with no margin for error, under pressure, for people who don't care how the machinery works. The wine was the product. The infrastructure was the job.

I've been managing a segmented home network behind pfSense for seven years. The homelab has been running for three. In 2025 I decided to stop treating it as a hobby.


---

## The Infrastructure

I don't run tutorials. I run a network I have to maintain, troubleshoot, and make real tradeoffs on.

**Beleriand — Three-Node Proxmox VE Cluster**
- Physical nodes: `Erebor` (10Gb), `Nogrod` and `Belegost` (2.5Gb), with a dedicated 1Gb Corosync network
- Six isolated network segments via VLAN-aware Linux bridge: VLAN 11 (Storage), VLAN 20 (Trusted), VLAN 30 (DMZ), VLAN 40 (IoT), VLAN 50 (Guest WiFi), VLAN 99 (Infrastructure)
- pfSense security gateway — stateful packet inspection, inter-VLAN routing, firewall policy
- `Aglarond` — TrueNAS SCALE VM on Erebor, 3× WD Red 4TB in RAIDZ1, NFS exports via custom StorageClass to all k3s workloads
- `Isengard` — Docker host on Erebor running Forgejo, Pi-hole, and Unifi Controller
- `Orthanc` — Home Assistant VM on Erebor
- `Pelargir` — Jellyfin VM on Nogrod with iGPU passthrough for hardware transcoding
- `Barazinbar` — Tailscale subnet router on Nogrod

**Kubernetes**
- Two-node k3s cluster spanning Nogrod and Belegost — control plane and worker separated across physical hosts
- `book-of-mazarbul` — air-gapped k3s stack for local AI and personal finance analysis. No data leaves the network.
- `learning-cluster` — GitOps-managed k3s environment. Flux, SOPS + age encryption, Kustomize overlays, Cloudflare Tunnel ingress.

The naming convention is Tolkien. Yes, all of it.

Manjaro Linux as a daily driver for seven years — not because a job required it.

---

## Active Repos

| Repo | What it is |
|------|------------|
| [learning-cluster](https://github.com/michael-bremser/learning-cluster) | k3s + Flux GitOps. Linkding deployed with SOPS-encrypted secrets and Cloudflare Tunnel ingress. Monitoring, Traefik, and image automation in progress. |
| [book-of-mazarbul](https://github.com/michael-bremser/book-of-mazarbul) | Air-gapped AI stack on k3s in Proxmox. Personal finance analysis. Zero external dependencies. |
| [pelargir](https://github.com/michael-bremser/pelargir) | Jellyfin on Proxmox with Intel Quick Sync hardware transcoding. Media on `aglarond` via NFS. Access via Tailscale from anywhere. |
| [dotfiles-bash](https://github.com/michael-bremser/dotfiles-bash) | Shell configuration and tooling. |

---

## Current Focus

Kubernetes certifications — CKAD target August 2026, CKA immediately after, CKS by end of year.

These are hands-on performance-based exams. Two hours, live cluster, no multiple choice. The homelab is the study environment.

---

## Stack

`Kubernetes` `k3s` `Flux` `Kustomize` `SOPS` `Helm` `Docker`
`Proxmox VE` `pfSense` `TrueNAS SCALE` `NGINX` `Cloudflare Tunnel` `Tailscale`
`Linux` `Git` `Bash` `VLAN` `NFS` `Pi-hole` `Forgejo` `Home Assistant`

---

## Background

Sommelier at [San Ysidro Ranch](https://www.sanysidroranch.com) — Forbes Five-Star property, one of the best wine programs on the West Coast. Before that, Beverage Manager at La Cumbre Country Club where I built a data model to automate consumption tracking and cut procurement waste.

The operational judgment transfers. The ability to learn hard things on purpose transfers. The tolerance for systems that break at 9pm on a Saturday definitely transfers.

[LinkedIn](https://linkedin.com/in/michael-bremser) · [Email](mailto:mike.bremser@gmail.com)
