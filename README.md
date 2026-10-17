# Getting-Started-ElasticWorkflows
# 🚀 Hands-On Elastic Stack SIEM Lab | SOC Analyst L1

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&pause=1000&color=00BFFF&center=true&vCenter=true&width=750&lines=Building+My+Own+SIEM+Lab;Learning+Elastic+Stack+Workflows;Practicing+Security+Monitoring;Developing+SOC+Analyst+L1+Skills" alt="Animated typing banner" />
</p>

<p align="center">
  <img src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" width="400" alt="Animated coding GIF" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-SOC%20Analyst%20L1-blue?style=for-the-badge" alt="SOC Analyst L1"/>
  <img src="https://img.shields.io/badge/Project-Hands--On%20Lab-00BFFF?style=for-the-badge" alt="Hands-on lab"/>
  <img src="https://img.shields.io/badge/SIEM-Elastic%20Stack-005571?style=for-the-badge" alt="Elastic Stack"/>
  <img src="https://img.shields.io/badge/Learning-In%20Progress-orange?style=for-the-badge" alt="Learning in progress"/>
</p>

## 📌 About This Project

Welcome to my **Hands-On Elastic Stack SIEM Lab**!

This repository documents my practical cybersecurity learning journey as I build and explore a Security Information and Event Management (SIEM) environment using the Elastic Stack.

My goal is to understand how SOC analysts collect security logs, search events, identify suspicious activity, investigate alerts, and learn security workflow automation.

I am using a virtual lab environment to develop practical skills relevant to an entry-level **SOC Analyst (Level 1)** role.

## 🎯 Project Objectives

- 🖥️ Build a home lab using VMware Workstation.
- 🐧 Install and configure Elasticsearch and Kibana on Ubuntu.
- 📊 Explore security data through Kibana.
- 🔍 Search Elasticsearch indexes and analyze event data.
- ⚙️ Build and test Elastic Workflows.
- 🚨 Learn how suspicious activity can be detected and investigated.
- 📝 Document practical exercises and troubleshooting steps.

## 🏗️ Lab Environment

| Component | Purpose |
|---|---|
| VMware Workstation | Virtual lab environment |
| Ubuntu Linux | Hosts the Elastic Stack |
| Elasticsearch | Stores, indexes, and searches data |
| Kibana | Provides dashboards, data exploration, and workflows |
| Elastic Agent | Collects supported endpoint logs |
| Windows 11 | Endpoint for Windows security log practice |
| Elastic Workflows | Automates sequences of tasks |

*Note: Components are introduced and integrated as the lab progresses.*

## 🔄 Understanding the SOC Workflow

<p align="center">
  <img src="https://img.shields.io/badge/01-Collect%20Logs-007ACC?style=for-the-badge" alt="Collect logs"/>
  <img src="https://img.shields.io/badge/02-Send%20Data-005571?style=for-the-badge" alt="Send data"/>
  <img src="https://img.shields.io/badge/03-Store%20%26%20Search-6A5ACD?style=for-the-badge" alt="Store and search"/>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/04-Detect%20Threats-orange?style=for-the-badge" alt="Detect threats"/>
  <img src="https://img.shields.io/badge/05-Investigate%20Alerts-red?style=for-the-badge" alt="Investigate alerts"/>
  <img src="https://img.shields.io/badge/06-Respond%20%26%20Document-228B22?style=for-the-badge" alt="Respond and document"/>
</p>

```text
Windows / Linux / Servers / Network Devices
                    |
                    v
              Elastic Agent
                    |
                    v
              Elasticsearch
           Store and index logs
                    |
                    v
                 Kibana
          Search and visualize data
                    |
                    v
          Detection Rules / Alerts
                    |
                    v
             SOC Analyst L1
                    |
                    v
          Investigate and Triage
                    |
                    v
       Document / Escalate / Respond
```

## 🧪 Hands-On Exercises

### 1. Elastic Stack Installation

- Installed Elasticsearch on Ubuntu.
- Configured and started the Elasticsearch service.
- Installed Kibana and completed its initial setup.
- Checked service status and tested Elasticsearch connectivity.

### 2. Exploring Elastic Workflows

- Navigated to **Management → Workflows**.
- Explored workflow structure and YAML configuration.
- Learned about manual triggers, inputs, steps, and console output.
- Practiced running a workflow and reading execution results.

### 3. Searching Elasticsearch Data

- Explored the `kibana_sample_data_logs` index.
- Created a search for HTTP `404` responses.
- Examined search results and the total number of matching documents.
- Learned how workflow steps can use the results of earlier steps.

### 4. Dynamic Workflow Automation

- Practiced conditional logic using an `if` step.
- Used a `wait` step to introduce a delay.
- Used a `foreach` step to process individual search results.
- Displayed failed request paths in workflow output.
- Explored how workflows handle both matching and non-matching results.

### 5. Windows Security Log Investigation

Planned practical exercises include:

- Reviewing Windows Event Viewer security events.
- Exploring successful logons (Event ID `4624`).
- Exploring failed logons (Event ID `4625`).
- Forwarding Windows security logs to Elastic.
- Investigating authentication activity through Kibana.

*The Windows log integration and investigation exercises will be documented as they are completed.*

## ⚙️ Example: Failed Web Request Workflow

The workflow searches sample web logs for HTTP `404` responses and checks whether matching documents exist.

```yaml
- name: elasticsearch_search_step
  type: elasticsearch.search
  with:
    index: "kibana_sample_data_logs"
    query:
      match:
        response: "404"
    size: 5
```

**Workflow logic:**

```text
Manual Trigger
      |
      v
Search Elasticsearch
      |
      v
Check Search Results
      |
      v
Are Results Greater Than 0?
      |
   +--+--+
   |     |
  YES    NO
   |     |
   v     v
Process  Display
Results  No Results
   |
   v
Display Failed Request Paths
```

This exercise demonstrates searching data, checking conditions, looping through results, and displaying useful output.

## 🧰 Skills I Am Developing

<p>
  <img src="https://img.shields.io/badge/Log%20Analysis-005571?style=flat-square" alt="Log analysis"/>
  <img src="https://img.shields.io/badge/SIEM-Elastic%20Stack-00BFB3?style=flat-square" alt="SIEM"/>
  <img src="https://img.shields.io/badge/Kibana-Dashboard%20%26%20Search-E8478B?style=flat-square" alt="Kibana"/>
  <img src="https://img.shields.io/badge/Linux-Ubuntu-E95420?style=flat-square" alt="Ubuntu"/>
  <img src="https://img.shields.io/badge/Windows-Security%20Logs-0078D4?style=flat-square" alt="Windows security logs"/>
  <img src="https://img.shields.io/badge/YAML-Workflow%20Configuration-CB171E?style=flat-square" alt="YAML"/>
</p>

- Security log analysis
- Elasticsearch queries
- Kibana data exploration
- Workflow automation fundamentals
- Conditional logic and loops
- Windows authentication event analysis
- Basic security alert investigation
- Linux administration and troubleshooting

## 📸 Lab Screenshots and Proof of Work

I will use this section to document evidence from my actual lab exercises.

| Exercise | Evidence to add |
|---|---|
| Elasticsearch installation | Service status and cluster response |
| Kibana setup | Kibana interface |
| Workflow creation | Workflow YAML editor |
| Workflow execution | Execution logs and step results |
| Elasticsearch search | Query and matching documents |
| Windows log investigation | Event details and corresponding Kibana events |


## 📚 Key Learning Takeaways

- Understand the basic flow of security data through the Elastic Stack.
- Learn how Elasticsearch searches return structured results.
- Understand how workflow inputs and outputs connect different steps.
- Use conditional logic to handle different search outcomes.
- Process multiple search results using loops.
- Connect workflow concepts to practical SOC investigation tasks.

## 🗺️ Future Lab Roadmap

- [ ] Explore Elastic Security detection rules and alerts.
- [ ] Build a suspicious-login investigation exercise.
- [ ] Document a complete SOC L1 triage workflow.

## 👨‍💻 About Me

I am a Computer Science graduate developing practical cybersecurity skills with a focus on **SOC Analyst Level 1**.

I use hands-on labs to strengthen my understanding of security monitoring, log analysis, SIEM tools, and incident investigation.

I created this repository to document my progress, share practical learning, and build a cybersecurity portfolio.

🔗 **GitHub:** [umairkhan404](https://github.com/umairkhan404)

🔗 TryHackMe: umairkhan404 

<p align="center">
  <a href="https://tryhackme.com/p/umairkhan404" target="_blank">
    <img
      src="https://user-images.githubusercontent.com/74038190/221352989-518609ab-b4d1-459e-929f-a08cd2bd9b3c.gif"
      width="100"
      alt="Visit My TryHackMe Profile"
    />
  </a>
  <br>
  <a href="https://tryhackme.com/p/umairkhan404">
    <strong>🔐 Visit My TryHackMe Profile</strong>
  </a>
</p>

---

<p align="center">
  <b>Learn by Building • Practice by Investigating • Improve by Documenting</b>
</p>

<p align="center">
  ⭐ If you find this project useful, consider giving the repository a star!
</p>
