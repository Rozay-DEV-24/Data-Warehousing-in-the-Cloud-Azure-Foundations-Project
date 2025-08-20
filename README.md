# ☁️ Data Warehousing in the Cloud — Azure Hands‑On

This project is a hands‑on walkthrough of **Azure data platform** primitives used to stand up a small, cloud‑native data stack: **Blob Storage** for files, **Azure SQL Database** (with the *SalesLT* sample schema) for relational queries, and surveys of **Cosmos DB** and **Azure-managed Postgres/MySQL** options for polyglot persistence. It was completed for *Introduction to Cloud Computing / Cloud Data Platform* (Assessment Week 6).

---

## 🎯 Objectives
- Create and secure an **Azure subscription** and resource group.
- Provision **Azure Storage (Blob)** and perform **upload/download** of block blobs.
- Create **Azure SQL Database**, connect, and **query** the *SalesLT* schema.
- Compare cloud data store models: **Cosmos DB (APIs & consistency)**, **PostgreSQL Hyperscale**, **Flexible Server** offerings for PostgreSQL/MySQL.
- Practice **governance & cost hygiene** with proper **cleanup** of resources.

---

## 🧱 Architecture (Minimal Lab Topology)
```
Local Machine  →  Azure Portal
                   ├─ Storage Account (Blob)  ──► Container (block blobs)
                   ├─ Azure SQL Database (SalesLT)  ──► Query Editor
                   └─ Docs deep‑dive: Cosmos DB, PostgreSQL Hyperscale, MySQL
```
Focus is on first‑party managed services and low‑ops setup via the web portal.

---

## 🛠️ Services & Tools
- **Azure Portal**, **Resource Groups**
- **Azure Storage (Blob)** — container + block blobs (upload/download)
- **Azure SQL Database** — *SalesLT* sample schema (tables: Address, Customer, Product, ProductCategory, ProductDescription, ProductModel, SalesOrderHeader/Detail, etc.)
- **Cosmos DB** — overview and **MongoDB API** (RU model, global distribution, tunable consistency)
- **Azure Database for PostgreSQL** — **Hyperscale (Citus)** nodes, distributed/reference/local tables; **Flexible Server**
- **Azure Database for MySQL** — Flexible/Single Server overviews
- Optional: **SQL Query Editor (in portal)**

---

## 🔎 What I Implemented
1. **Azure account & RG** set‑up with portal.
2. **Blob storage container** created; verified **upload & download** of a test file.
3. **Azure SQL Database** provisioned; executed **SELECT** queries against **SalesLT** and documented **keys, data types, and foreign‑key relationships**.
4. Summarized trade‑offs across **NoSQL vs. relational**, **Cosmos DB** (global distribution, RU throughput, consistency), and **Hyperscale Postgres** (coordinator/workers, sharding, distributed/reference tables).

---

## 🧪 Reproduce the Lab
1. **Sign up** at Azure Portal → create **Resource Group**.
2. **Storage Account → Containers** → create container → **Upload** a small file → **Download** to verify.
3. **Azure SQL** → create **Single Database** → choose compute tier → select sample data → **Query Editor** to run sample joins over **SalesLT**.
4. (Optional) Create **Cosmos DB** account (**MongoDB API**) to explore RU/consistency; review **PostgreSQL Hyperscale** & **Flexible Server** docs.
5. **Clean up**: delete RG to remove all resources and stop charges.

---

## 🧠 Key Learnings
- **Polyglot persistence:** choose the store that fits the workload (relational vs. key‑value/document/graph).
- **Managed services** reduce ops toil: backup, HA, patching, and scaling are handled by Azure.
- **Cost & performance** are first‑class: DTU/vCore tiers for SQL; **RU/s** for Cosmos DB; **scale‑out** for Hyperscale Postgres.
- **Data modeling matters:** *SalesLT* shows normalized design with clear PK/FK relations that drive query patterns.

---

## 🧹 Cleanup
Always delete the **Resource Group** when done to avoid ongoing costs.

---

## 📁 Repo Structure (suggested)
```
/docs
  └─ screenshots/        # Portal screenshots (optional)
/sql
  └─ sample_queries.sql  # Example queries against SalesLT
README.md                # This file
```

---

## 👤 Author
**Rohit Surya** — Provisioning, storage & SQL setup, schema analysis, service trade‑off summaries.

---

## 📄 License
Academic use only.
