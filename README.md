# N4j-DPKG
Design Pattern Knowledge Graph

# 🧠 Design Pattern Knowledge Graph (DPKG)

**DPKG** is an experimental framework for parsing open-source code (starting with Python) and constructing a **knowledge graph representation** of its **design pattern relationships**.

> 🚧 **This project is currently in an early, exploratory phase focused on static parsing and semantic graph construction. Functionalities built on top of the graph will be developed in later stages.**

---

📌 What is DPKG?

DPKG extracts a **design-level structure** from a GitHub module or local Python codebase, then models this structure as a **graph** in Neo4j.

- **Nodes** represent:
  - `Classes`, `Functions`, `Modules`, and `Design Patterns`
- **Edges** represent:
  - Structural or design relationships like `EXTENDS`, `USES`, `COMPOSED_OF`, `DECORATES`, etc.

---

## Core Concepts

| Concept              | Description                                                  |
|----------------------|--------------------------------------------------------------|
| 🧩 **Design Pattern Graph** | A semantic graph capturing architectural intent and structure |
| 📂 **GitHub Modules**       | Parsed Python repositories used as source input            |
| 📊 **Neo4j Representation** | The result is a traversable, visualizable design graph      |

---

## 📐 Graph Schema (Experimental v0.1)

```plaintext
(:Module)-[:CONTAINS]->(:Class)
(:Class)-[:EXTENDS]->(:Class)
(:Class)-[:FOLLOWS_PATTERN]->(:Pattern)
(:Function)-[:DECORATES]->(:Function)
(:Class)-[:USES]->(:Function)
