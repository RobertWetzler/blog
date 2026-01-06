---
title: "Resume"
layout: "single"
type: "resume"
---

# Robert Wetzler

**Seattle, WA** · [github.com/RobertWetzler](https://www.github.com/RobertWetzler) · [rwetzler779@gmail.com](mailto:rwetzler779@gmail.com) · [linkedin.com/in/RobertWetzler](https://www.linkedin.com/in/RobertWetzler)

# Work Experience

## Microsoft — Azure Storage, Seattle, WA

### Software Engineer II · *August 2022 – Present*

**Lead Engineer & Architect of new Azure Storage Repair Services**, critical infrastructure in enabling Azure Storage's transition to a next-generation hosting platform, supporting a 10x scalability increase

- Designed and built foundational Azure microservice from scratch using modern C# ASP.NET Core, led buildout reaching global availability across 450+ geodistributed baremetal nodes
- Grew microservice into a distributed system of four services communicating over gRPC offering modern repair, safety, and health APIs for fundamental operations across Azure Storage
- Implemented stateful services with fault tolerance, upgrade domains, rollback, and OpenTelemetry tracing
- Spearheaded security designs involving auth/z (delegated OAuth2, RBAC) and auto-renewing certificates
- Implemented release protocols including automated testing and staged deployments

**Developed a real-time distributed log search API** reducing search times from 5+ minutes to instantaneous

- Utilized C++ per-node agents that stream results to a C# aggregator server, using a multi-threaded algorithm capable of combining streams at a rate of 100 MB/s to the frontend portal

**Developed synthetics framework** to scan for API issues in production

- Developed API scanner via Swagger that automatically detects critical service failures

### Software Engineer Intern · *May – July 2021*

- Designed and built diagnostics portal for Azure Storage aggregating real-time health data — Angular, C++

## Western Digital, Rochester, MN

### Software Engineer Co-Op · *January – August 2020*

- Developed a disk testing automation framework for the testing lab — Python

## Ohio State University Digital Flagship, Columbus, OH

### Application Developer · *January 2019 – 2022*

- Developed an iOS app for Ohio State to help students learn about the campus — Unity, C#, & Swift

# Software Projects

## Social Media App
*Personal Project (2025)* · [cliq-server.fly.dev](https://cliq-server.fly.dev)

- Privacy-focused social media enabling granular sharing of posts/events via "Circles" with real-time engagement
- Utilized: React Native, C#, ASP.NET Core, Postgres, Docker, Fly.io, JWT Auth, Typescript, iOS Notifications

## Backpackable Astrophotography Camera
*Personal Project (2024)*

- Co-developed triple-axis camera gimbal, capable of tracking any star/planet fully offline
- Utilized: Linux (Hostapd, Systemd), embedded Python server, Javascript client, Raspberry Pi

## Climate Analytics Portal
*Capstone Project (2022)*

- Developed full-stack dashboard for Ohio State Climatology office for visualizing real-time climate data
- Utilized: Python, Django, Javascript, ApexCharts.js

# Education

## The Ohio State University
**B.S. Computer Science Engineering** · *Graduated May 2022* · GPA: 3.9

# Qualifications

**Skills**: Primarily backend, cloud, and distributed systems (C#, C/C++, Python, Java, Postgres, React, AWS, Azure)

**Grand Prize** — Ohio State University's Hackathon "HACK OH/IO," 2020 (AI Social-Distancing Detector)

**Best Designed Award** — Ohio State University's Hackathon "HACK OH/IO," 2018
