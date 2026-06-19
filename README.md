# TheLayer0Guide — Cheat Sheets

A collection of dark-themed, offline-capable reference sheets for CLI tools, DevOps, programming languages, security, and more. Built as a static website — no framework, no build step, no CDN dependency beyond Google Fonts.

**[→ Open the Index](index.html)**

---

## What's inside

111 reference sheets across five categories:

| Category | Topics |
|---|---|
| **Cloud & Infra** | Kubernetes, Docker, Podman, Helm, OpenStack, VMware, Terraform, Ceph, Prometheus, ArgoCD, … |
| **System & Netz** | Bash, tmux, vim, SSH, systemd, iptables, nmcli, LVM, OpenSSL, tcpdump, … |
| **Security** | nmap, Metasploit, Burp Suite, Hydra, Hashcat, Wireshark, netcat, sqlmap, … |
| **Development** | Python, Go, Rust, Java, TypeScript, C/C++, Git, Ansible, GitLab CI, Make, … |
| **Daten & Office** | SQL, PostgreSQL, MariaDB, MongoDB, Redis, Excel, LibreOffice, Markdown, … |

---

## Features

- **Instant search** — results ranked by name match → tag match → content match
- **Category filter** with nested subgroups (Container, OpenStack, VMware, Shell, …)
- **A-Z sort** toggle
- **Fully offline** after the initial page load (single HTML file per sheet, no JS bundles)
- **Consistent dark theme** — JetBrains Mono + Syne, syntax-highlighted code blocks

---

## Structure

```
cheat-sheets/
├── index.html              Main page — filter, search, card grid
├── sheets/                 One HTML file per cheat sheet
│   ├── python-cheatsheet.html
│   ├── kubernetes-cheatsheet.html
│   └── …
├── assets/                 SVG icons (one per tool)
└── md/
    ├── style.md            Design system — colors, components, rules
    ├── sheet-template.md   Canonical HTML template for new sheets
    └── inventory.md        Full inventory of all 111 sheets
```

---

## Adding a new sheet

1. Copy `md/sheet-template.md` and adapt it to the new tool's style guide.
2. Save as `sheets/{tool}-cheatsheet.html`.
3. Add an SVG icon to `assets/{tool}.svg`.
4. Register a card in `index.html`:
   - Add a `.c-{tool}` CSS color theme (accent + surface + border variants).
   - Add the `<a class="card c-{tool}" …>` block with `data-title`, `data-group`, and `data-subgroups`.
   - Update the pill counts in the toolbar (or rely on the JS auto-sync).
5. Consult `md/style.md` for all naming conventions and `md/inventory.md` for existing entries.

---

## Tech stack

| Layer | Choice |
|---|---|
| Markup | Vanilla HTML5 |
| Styling | Inline CSS (no preprocessor) |
| Interactivity | ~150 lines of vanilla JS (filter + search + sort) |
| Fonts | JetBrains Mono · Syne (Google Fonts CDN) |
| Icons | Custom SVG per tool |
| Hosting | Any static file server / GitHub Pages |

---

## License

Content is provided for educational and reference purposes. Tool names and logos are trademarks of their respective owners.
