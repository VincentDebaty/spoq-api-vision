# SPOQ Master API Vision

> **One unified platform for all SPOQ data**

---

## 📋 Executive Summary

SPOQ Master API is our strategic initiative to **unify all SPOQ data** into a single, reliable source of truth.

**Key Points:**
- ✅ **One database** for all applications
- ✅ **Real-time sync** between legacy and new apps
- ✅ **Open platform** for partners and AI integrations

---

## 🔴 The Problem Today

### Current State: Fragmented Data

```mermaid
graph TB
    subgraph "Today's Reality"
        SPOQ[(SPOQ Database)]
        FORMS1[(Forms - Tenant A)]
        FORMS2[(Forms - Tenant B)]
        FORMS3[(Forms - Tenant C)]
    end

    SPOQ -.->|Manual sync?| FORMS1
    SPOQ -.->|Inconsistent| FORMS2
    SPOQ -.->|Delayed| FORMS3

    style SPOQ fill:#f44336
    style FORMS1 fill:#ff9800
    style FORMS2 fill:#ff9800
    style FORMS3 fill:#ff9800
```

### Pain Points

| Issue | Impact |
|-------|--------|
| 🔄 **Data silos** | Same client exists differently in each system |
| ⏱️ **No real-time sync** | Changes take time to propagate |
| 🔧 **Hard to maintain** | Every new app needs custom integrations |
| 🚫 **No partner access** | External partners can't connect easily |
| 🤖 **No AI readiness** | Can't leverage modern automation tools |

---

## 🟢 The Solution: SPOQ Master API

### Central Hub Architecture

```mermaid
graph TB
    subgraph "All Applications"
        SPOQ[SPOQ]
        FORMS[Forms]
        WC[Web Components]
        PARTNERS[Partners]
        AI[AI Agents]
    end

    subgraph "SPOQ Master"
        API[Master API]
        DB[(Central Database)]
    end

    SPOQ <-->|Sync| API
    FORMS <-->|Sync| API
    WC -->|REST API| API
    PARTNERS -->|REST API| API
    AI -->|REST API| API

    API --> DB

    style API fill:#4caf50,color:#fff
    style DB fill:#2196f3,color:#fff
```

### Key Benefits

| Benefit | Description |
|---------|-------------|
| 🎯 **Single Source of Truth** | One database, one version of data |
| ⚡ **Real-time Updates** | Changes sync in less than 1 second |
| 🔌 **Easy Integration** | Standard REST API for all apps |
| 🤝 **Partner Ready** | External partners can connect via API |
| 🤖 **AI Ready** | Built for automation and AI tools |
| 🛡️ **Resilient** | If an app is down, data syncs automatically when it's back |

---

## ⚙️ How It Works

### Simple Flow

```mermaid
graph LR
    subgraph "Any App"
        APP[Your App]
    end

    subgraph "SPOQ Master"
        API[API]
        DB[(Database)]
    end

    subgraph "All Other Apps"
        OTHERS[Other Apps]
    end

    APP -->|1. Make change| API
    API -->|2. Store| DB
    API -->|3. Notify| OTHERS

    style API fill:#4caf50,color:#fff
```

### What Happens When You Create a Job?

```mermaid
sequenceDiagram
    participant You as Your App
    participant API as Master API
    participant DB as Database
    participant Others as All Other Apps

    You->>API: Create new job
    API->>DB: Save job
    API-->>You: ✅ Done!
    API->>Others: 📢 "New job created"
    Others->>Others: Update their view
```

**Result:** All apps see the same job, instantly.

---

## 🗓️ Evolution Roadmap

### Three Phases

```mermaid
graph LR
    subgraph "Phase 1"
        P1[Current State]
    end

    subgraph "Phase 2"
        P2[Transition]
    end

    subgraph "Phase 3"
        P3[Target State]
    end

    P1 -->|"Deploy API"| P2
    P2 -->|"Migrate apps"| P3

    style P1 fill:#f44336,color:#fff
    style P2 fill:#ff9800,color:#fff
    style P3 fill:#4caf50,color:#fff
```

### Phase Details

| Phase | State | Description |
|-------|-------|-------------|
| **Phase 1** 🔴 | Current | Separate databases, no sync |
| **Phase 2** 🟠 | Transition | Master API + auto-sync with legacy apps |
| **Phase 3** 🟢 | Target | All apps use the API directly |

### Visual Timeline

```mermaid
gantt
    title SPOQ Master API Roadmap
    dateFormat  YYYY-MM
    section Phase 2
    Master API Live           :2026-03, 2026-06
    SPOQ Sync Active          :2026-04, 2026-07
    Forms Sync Active         :2026-05, 2026-08
    Partner Portal            :2026-06, 2026-09
    section Phase 3
    SPOQ Migration            :2026-09, 2027-03
    Forms Migration           :2026-12, 2027-06
    Full API First            :2027-06, 2027-09
```

---

## 👥 Benefits for Stakeholders

### For Clients

```mermaid
graph LR
    A[📱 Partner Portal] --> B[View their jobs]
    A --> C[Track progress]
    A --> D[Access reports]

    style A fill:#e91e63,color:#fff
```

- ✅ Self-service portal to view their data
- ✅ Real-time status updates
- ✅ Direct access to reports and certificates

### For Partners

```mermaid
graph LR
    A[🔌 API Access] --> B[Integrate systems]
    A --> C[Automate workflows]
    A --> D[Get notifications]

    style A fill:#9c27b0,color:#fff
```

- ✅ Connect their own systems to SPOQ
- ✅ Receive webhooks for events
- ✅ Build custom integrations

### For Internal Team

```mermaid
graph LR
    A[🛠️ One Platform] --> B[Faster development]
    A --> C[Less maintenance]
    A --> D[Better reliability]

    style A fill:#2196f3,color:#fff
```

- ✅ Build new features faster
- ✅ One API to maintain, not many
- ✅ Clear data model

---

## 🔒 Security & Access Control

### Data Isolation

```mermaid
graph TB
    subgraph "SPOQ Master API"
        API[API Gateway]
        AUTH[Authentication]
        AUTHZ[Authorization]
    end

    subgraph "Access Levels"
        INTERNAL[Internal Apps<br/>Full Access]
        PARTNER[Partners<br/>Own Data Only]
        CLIENT[Clients<br/>Read Own Jobs]
        AI[AI Tools<br/>Limited Scope]
    end

    API --> AUTH
    AUTH --> AUTHZ

    AUTHZ -->|Admin scope| INTERNAL
    AUTHZ -->|Partner scope| PARTNER
    AUTHZ -->|Client scope| CLIENT
    AUTHZ -->|AI scope| AI

    style AUTH fill:#f44336,color:#fff
    style AUTHZ fill:#ff9800,color:#fff
```

### Key Principles

| Principle | Description |
|-----------|-------------|
| 🔐 **Data Isolation** | Partners and clients only see their own data |
| 🎫 **Role-Based Access** | Different permissions for internal apps, partners, clients |
| 🤖 **AI Limitations** | Automation tools have restricted, read-only access |
| 🔑 **JWT Authentication** | Secure tokens via Keycloak |
| ⏱️ **Rate Limiting** | Request limits per user type to ensure fair usage |

### Who Sees What?

| User Type | Access | Rate Limit |
|-----------|--------|------------|
| **Internal Apps** | Full access to all data | Unlimited |
| **Partner** | Only their clients and jobs | 1000 req/min |
| **Client** | Only their own jobs and reports | 100 req/min |
| **AI Agent** | Limited queries, no sensitive data | 60 req/min |

---

## 🤖 AI-Ready Platform

### Modern Automation

```mermaid
graph TB
    subgraph "AI & Automation"
        N8N[N8N Workflows]
        CHAT[AI Assistants]
        AGENTS[Custom Agents]
    end

    subgraph "SPOQ Master API"
        API[API]
        TOOLS[AI Tools Endpoint]
        HOOKS[Webhooks]
    end

    N8N -->|Automate| API
    CHAT -->|Query| API
    AGENTS -->|Actions| TOOLS

    API -->|Notify| N8N
    HOOKS -->|Events| N8N

    style API fill:#4caf50,color:#fff
    style TOOLS fill:#9c27b0,color:#fff
```

### Use Cases

| Automation | Description |
|------------|-------------|
| 📧 **Auto-notifications** | When job completes → Email client automatically |
| 📊 **CRM Sync** | New client → Create in Odoo |
| 🤖 **AI Assistant** | "Schedule an EPC inspection for client X" |
| 📋 **Reporting** | Daily job summary → Slack channel |

### AI Integration Features

- 📄 **llms.txt** - Machine-readable API description
- 🔧 **Tools Endpoint** - Ready for AI function calling
- 📡 **Webhooks** - Trigger automations on any event
- 📖 **Rich Documentation** - AI can understand and use the API

---

## 🚀 Next Steps

### Immediate Actions

```mermaid
graph LR
    A[1. Approve Vision] --> B[2. Setup Infrastructure]
    B --> C[3. Deploy API]
    C --> D[4. Connect First App]

    style A fill:#4caf50,color:#fff
    style B fill:#2196f3,color:#fff
    style C fill:#ff9800,color:#fff
    style D fill:#e91e63,color:#fff
```

### Key Milestones

| Milestone | Target |
|-----------|--------|
| ✅ Vision approved | This meeting |
| 🔧 Infrastructure ready | +2 weeks |
| 🚀 API deployed (staging) | +4 weeks |
| 🔗 First app connected | +6 weeks |
| 📢 Partner portal beta | +3 months |

---

## ❓ Questions?

### Key Points to Remember

1. **One database** = One source of truth
2. **Real-time sync** = No more inconsistencies
3. **Open platform** = Partners and AI can connect
4. **Secure by design** = Each user only sees their own data
5. **Gradual migration** = No big bang, step by step

---

*Document prepared for SPOQ Master API Vision Meeting - January 2026*
