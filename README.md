# 01 Cyber Range Blue Team

A downloadable, beginner-to-advanced cyber defense lab for learning blue-team investigation, log review, alert triage, detection engineering, and incident reporting in a safe local environment.

This project is built for **authorized local lab training only**. It uses **sample logs, simulated security events, and harmless containers**. It does not contain malware, credential theft tooling, persistence tooling, exploitation tooling, or instructions for attacking real systems.

---

## Project Overview

`01-cyber-range-blue-team` is a self-contained cyber defense range designed to teach practical security operations skills through progressively harder labs.

The range includes:

- Docker-based local lab environment
- Simulated web service that produces training logs
- Log generator for fake Linux, authentication, web, process, network, and file-integrity events
- Defensive monitoring container that reads logs and emits alerts
- Dashboard placeholder for future visualization
- Sample logs for offline practice without Docker
- Sigma-style detection examples
- Python detection scripts
- Bash one-liner examples
- Incident response report template
- Final capstone investigation

---

## Skills Learned

By completing this project, learners practice:

- Linux log review
- Authentication failure analysis
- Web access log analysis
- Suspicious process review
- Brute-force pattern recognition
- File integrity monitoring concepts
- Network connection review
- Incident timeline creation
- Alert triage and severity scoring
- Detection logic development
- Writing incident response reports
- Communicating findings professionally

---

## Difficulty Levels

| Level | Labs | Focus |
|---|---:|---|
| Beginner | 01-03 | Reading logs, identifying basic indicators, understanding fields |
| Intermediate | 04-07 | Correlating events, recognizing patterns, using detections |
| Advanced | 08-10 | Building timelines, triaging alerts, completing a capstone investigation |

---

## Repository Structure

```text
01-cyber-range-blue-team/
├── README.md
├── LEARNING_PATH.md
├── REPORT_TEMPLATE.md
├── docker/
│   ├── docker-compose.yml
│   ├── dashboard/
│   ├── log-generator/
│   ├── monitor/
│   └── web-service/
├── docs/
├── labs/
├── scripts/
├── detections/
│   ├── bash/
│   ├── json-alerts/
│   ├── python/
│   └── sigma/
├── sample-logs/
├── reports/
└── assets/
```

---

## Docker-Based Lab Components

| Component | Purpose | Safety Note |
|---|---|---|
| `web-service` | Harmless simulated web service that writes web-style logs | No real exploitation logic |
| `log-generator` | Creates fake auth, process, network, web, and FIM logs | Sample telemetry only |
| `monitor` | Reads local logs and creates JSON alerts | Defensive detection only |
| `dashboard` | Static placeholder dashboard | No external connections required |

---

## Install Instructions

### Requirements

- Git
- Docker Desktop or Docker Engine
- Docker Compose v2
- Python 3.10+ for running detection scripts outside Docker
- PowerShell 7+ recommended on Windows, macOS, or Linux

### Clone the Repository

```powershell
git clone https://github.com/YOUR-USERNAME/01-cyber-range-blue-team.git
cd 01-cyber-range-blue-team
```

### Start the Docker Lab

```powershell
docker compose -f docker/docker-compose.yml up --build
```

### Open the Local Services

| Service | URL |
|---|---|
| Simulated web service | `http://localhost:8080` |
| Dashboard placeholder | `http://localhost:8088` |

### Stop the Lab

```powershell
docker compose -f docker/docker-compose.yml down
```

### Run Detection Scripts Locally

```powershell
python .\scripts\run_all_detections.py
```

### Run with Helper Scripts

```powershell
.\scripts\start-lab.ps1
.\scripts\run-detections.ps1
.\scripts\stop-lab.ps1
```

---

## Screenshots Placeholder

Add screenshots after running the lab:

| Screenshot | Description | Path |
|---|---|---|
| Dashboard Home | Static defensive dashboard view | `assets/screenshots/dashboard-home.png` |
| Web Service | Simulated service landing page | `assets/screenshots/web-service.png` |
| Monitor Output | Defensive alerts in terminal | `assets/screenshots/monitor-output.png` |
| Capstone Report | Completed incident report | `assets/screenshots/capstone-report.png` |

---

## Hands-On Labs

| Lab | Title | Primary Skill |
|---:|---|---|
| 01 | Linux Log Review | Reading log format and extracting fields |
| 02 | Failed Login Detection | Authentication review |
| 03 | Suspicious Process Detection | Process event analysis |
| 04 | Web Attack Log Analysis | Web log investigation |
| 05 | Brute-Force Pattern Recognition | Pattern and threshold detection |
| 06 | File Integrity Monitoring | Change review and file event triage |
| 07 | Network Connection Review | Connection and destination review |
| 08 | Incident Timeline Building | Correlation and ordering |
| 09 | Alert Triage | Prioritization and severity scoring |
| 10 | Final Capstone Investigation | Full investigation and reporting |

Start here:

```powershell
Get-ChildItem .\labs\*.md | Sort-Object Name
```

---

## Lab Completion Checklist

Use this checklist to track progress.

- [ ] Read `docs/local-only-safety.md`
- [ ] Start the Docker lab
- [ ] Open the dashboard placeholder
- [ ] Review all files in `sample-logs/`
- [ ] Complete Lab 01: Linux Log Review
- [ ] Complete Lab 02: Failed Login Detection
- [ ] Complete Lab 03: Suspicious Process Detection
- [ ] Complete Lab 04: Web Attack Log Analysis
- [ ] Complete Lab 05: Brute-Force Pattern Recognition
- [ ] Complete Lab 06: File Integrity Monitoring
- [ ] Complete Lab 07: Network Connection Review
- [ ] Complete Lab 08: Incident Timeline Building
- [ ] Complete Lab 09: Alert Triage
- [ ] Complete Lab 10: Final Capstone Investigation
- [ ] Run every Python detection script
- [ ] Review Sigma-style rules
- [ ] Use Bash one-liners against sample logs
- [ ] Complete `REPORT_TEMPLATE.md`
- [ ] Save the finished report in `reports/`

---

## Learning Outcomes

After completing the range, students should be able to:

1. Explain the purpose of common Linux and web logs.
2. Identify failed login spikes and brute-force-like patterns in sample data.
3. Recognize suspicious process and file-change events in training logs.
4. Convert suspicious observations into structured alerts.
5. Correlate multiple log sources into a timeline.
6. Triage alerts based on severity, confidence, and evidence.
7. Write a clear incident report with scope, timeline, findings, and recommendations.
8. Understand how detection rules, scripts, and analyst judgment support each other.

---

## Safety and Legal Disclaimer

This repository is for **authorized local lab training only**. It contains simulated logs and benign defensive training code. Do not use this project to attack, scan, disrupt, or access systems that you do not own or do not have explicit written permission to test.

The project does **not** include real malware, credential theft, persistence mechanisms, destructive payloads, or instructions for attacking real systems.

---

## Suggested Next Improvements

- Add real dashboard panels later using Grafana, OpenSearch, or another local-only SIEM stack.
- Add unit tests for detection scripts.
- Add more sample logs for Windows Event Log-style analysis.
- Add scoring for lab answers.
- Add a release package for classrooms or team training.
