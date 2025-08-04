# 🧠 Nebulai AgentSpace – Arsitektur Sistem

Dokumentasi ini menjelaskan proses kerja sistem agent dalam proyek Nebulai AgentSpace berdasarkan diagram berikut:

![Architecture Diagram](../img/agent_architecture_diagram.png)

---

## 🔧 Komponen Utama

### 🔹 Pioneer
Inisiator awal sistem yang memulai task dan menentukan tag, seperti:  
{ tag: 1+4, task: "Generate report" }

### 🔹 Origin Agent (Root Agent)
Memilih agent dari Agent Cluster berdasarkan tag yang cocok. Menilai semua hasil dan menentukan output terbaik.

### 🔹 Agent Cluster
Kumpulan agent (A, B, C, D, dll) yang punya tag tertentu. Misal:  
- Agent A: tag 1  
- Agent B: tag 2  
- Agent E: tag 1+2

---

## 🔁 Alur Proses

1. Pioneer mengirim task dan tag ke Root Agent.
2. Root Agent memilih agent dari cluster berdasarkan tag.
3. Tugas dikirim ke agent.
4. Semua hasil dikumpulkan, dinilai, dan hasil akhir dikembalikan.

---

## 📦 Contoh Agent

```json
{
  "url": "https://nebulai.agent/agent-1",
  "name": "Agent 1",
  "tag": [1, 3, 4]
}
