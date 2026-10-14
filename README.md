<div align="center">
  <img src="./banner.png" width="60%" alt="lofi coder banner"/>
</div>

<br/>

<div align="center">
  <h1>👋 Hey, I'm Shubhojyoti Datta Chaudhuri</h1>
  <h3>Software Engineer • Backend, Full-Stack & AI/ML Systems • MS Computer Science @ University at Buffalo</h3>
</div>
<br/>
<div align="center">
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&duration=3000&pause=800&color=7EC8E3&center=true&vCenter=true&width=700&height=32&lines=Measuring+GPU+energy+per+LLM+request+in+Rust;Distributed+backends+%7C+Full-stack+apps+%7C+AI%2FML+systems;Rust+%7C+Python+%7C+TypeScript+%7C+CUDA+%7C+Triton;Graduating+Feb+2027+%E2%80%94+open+to+SWE+%26+ML+roles)](https://github.com/Shub1806)
 
</div>
<br/>
<div align="center">
[![Portfolio](https://img.shields.io/badge/-Portfolio-000000?style=flat-square&logo=vercel&logoColor=white)](https://shubhojyoti-portfolio.vercel.app)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/shubhojyotidatta)
[![Gmail](https://img.shields.io/badge/-shubdc1806@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:shubdc1806@gmail.com)
[![GitHub](https://img.shields.io/badge/-Shub1806-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Shub1806)
[![Buffalo NY](https://img.shields.io/badge/-Buffalo%2C%20NY-6c757d?style=flat-square&logo=googlemaps&logoColor=white)]()
 
</div>
---
 
# 🎓 About Me
 
I'm a software engineer with a **12-month software engineering internship** and a **client project** behind me, currently pursuing an **M.S. in Computer Science (AI/ML Track)** at the **University at Buffalo**, graduating **February 2027**.
 
I build backend services, full-stack applications, and AI/ML systems in **Python, TypeScript, and Rust**. Recently that has meant a Rust gateway that measures per-request GPU energy for LLM inference, a distributed email client running on Redis Streams workers, and a Snowflake/PySpark pipeline over 32M records.
 
I debug to root cause, ship with tests and CI, and I'm open to **Software Engineering** and **Machine Learning** roles.
 
---
 
# 🚀 Projects
 
## ⚡ Wattson — Per-Request GPU Energy for LLM Inference · `Rust` `CUDA` `Triton` `vLLM` `Python`
 
> An async Rust gateway in front of vLLM that tells you how much GPU energy each individual request actually used.
 
- Built with **axum/tokio**, attributing NVML-measured GPU energy to each request through a 20 ms time-sliced, phase-weighted, queue-aware ledger, which fixed a **4x overcount** in naive measurement.
- On a **Tesla T4**, vLLM batching cut energy per token **13x** versus serial Hugging Face (1.34 → 0.10 J/token) and raised throughput **17x**.
- Roofline analysis traced decode running 10x off the memory floor back to kernel launch overhead.
- Wrote a fused residual-add + RMSNorm kernel in **CUDA** (warp shuffles, `half2`) and **Triton** that reaches **71% of peak memory bandwidth**, running **5.6x faster** with **5.5x less energy** per call than PyTorch eager.
---
 
## 📬 triage/mail — AI Email Triage Client · `Python` `FastAPI` `Redis Streams` `PostgreSQL` `React` `Ollama`
 
> A Gmail and Outlook client that ranks your inbox by priority and learns from your corrections.
 
- Priority ranking through a **rules → TF-IDF/logistic regression → local LLM** cascade that extracts deadlines from no-reply emails, flags scams, and retrains nightly from user feedback.
- Distributed backend of sync, classify, send, and scheduler workers on **Redis Streams consumer groups**, with re-delivery, a dead-letter queue, an exactly-once outbox with undo, and a leader-elected scheduler.
- **React + TypeScript** client with a typed client for **39 REST endpoints**, optimistic updates, and live WebSocket updates; sign-in secured with **OAuth 2.0 PKCE** and encrypted tokens.
- Fixed a start-up race with a Postgres advisory lock (crashes went from 7 of 8 runs to 0 of 8), and fixed a merge bug that raised priority accuracy from **53% → 63%** on hand-labeled emails.
- **54 tests** running in CI.
---
 
## 💽 Drive Health Monitor — Anomaly Detection & Validated RAG · `Snowflake` `PySpark` `scikit-learn` `Ollama`
 
> A data pipeline and anomaly-detection system for spotting failing hard drives across tens of millions of telemetry records.
 
- **Snowflake/PySpark** bronze/silver/gold pipeline over **31,968,003 drive records**, with quality gates at each stage.
- Evaluated a rule baseline against **Isolation Forest** using precision@k, landing at roughly **60–80x the base rate**.
---
 
# 💼 Experience
 
### Software Developer (Client Project)
**LookThePart – University at Buffalo**
 
**Jan 2026 – Jun 2026** • Remote
 
- Built **2 new Django endpoints** and extended **12 existing** post and product endpoints (post create/edit/display, featured posts, product create/edit/batch upload, affiliate mapping) through Git pull requests.
- Improved product search in the **Swift (UIKit) iOS app**, with better autocomplete suggestions and search results backed by the Django REST product search API via Alamofire.
- Integrated the **Wix Blog API** to auto-generate blog drafts, then diagnosed a production **504 timeout** caused by processing 40 images sequentially per request; fixed it by caching generated watermarks and adding a live progress modal.
---
 
### Software Engineer Intern
**VertexPlus Technologies Limited**
 
**Jun 2024 – May 2025** • India
 
- Co-developed a window-sticker **OCR pipeline** in Python with **OpenCV** and **Tesseract** for a US automotive platform, extracting VIN, specs, and features into structured JSON for a Django REST API and AWS S3.
- Implemented layout detection with OpenCV template matching against **33 manufacturer logo templates** at a 0.8 confidence threshold, routing each image to one of **12 layout-specific parsers** covering **18+ vehicle brands**.
- Co-designed the **Vehicle IQ** collision-prevention scoring algorithm, weighting normalized safety features with parent/child feature expansion and scoring against both dealer data and the NHTSA vPIC VIN decoder.
---
 
# 🎓 Education
 
**University at Buffalo, The State University of New York** — Buffalo, NY
M.S. Computer Science, AI/ML Track • GPA 3.7/4.0 • Aug 2025 – Feb 2027
*Coursework:* Algorithms (A), Operating Systems, Deep Learning
 
**Chandigarh University** — India
B.E. Computer Science • Aug 2021 – May 2025
 
---
 
# 🛠️ Tech Stack
 
### Languages
 
![Python](https://img.shields.io/badge/Python-3d6b8c?style=flat-square&logo=python&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-3d6b8c?style=flat-square&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3d6b8c?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-3d6b8c?style=flat-square&logo=javascript&logoColor=white)
![Java](https://img.shields.io/badge/Java-3d6b8c?style=flat-square&logo=openjdk&logoColor=white)
![C](https://img.shields.io/badge/C-3d6b8c?style=flat-square&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-3d6b8c?style=flat-square&logo=cplusplus&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-3d6b8c?style=flat-square&logo=nvidia&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-3d6b8c?style=flat-square&logo=swift&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-3d6b8c?style=flat-square&logo=postgresql&logoColor=white)
![HTML/CSS](https://img.shields.io/badge/HTML%2FCSS-3d6b8c?style=flat-square&logo=html5&logoColor=white)
![Shell](https://img.shields.io/badge/Shell-3d6b8c?style=flat-square&logo=gnubash&logoColor=white)
 
### AI & GPU
 
![PyTorch](https://img.shields.io/badge/PyTorch-7a5c8c?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging_Face-7a5c8c?style=flat-square&logo=huggingface&logoColor=white)
![vLLM](https://img.shields.io/badge/vLLM-7a5c8c?style=flat-square&logoColor=white)
![Triton](https://img.shields.io/badge/Triton-7a5c8c?style=flat-square&logoColor=white)
![NVML](https://img.shields.io/badge/NVML-7a5c8c?style=flat-square&logo=nvidia&logoColor=white)
![Roofline Analysis](https://img.shields.io/badge/Roofline_Analysis-7a5c8c?style=flat-square&logoColor=white)
![LLMs](https://img.shields.io/badge/LLMs-7a5c8c?style=flat-square&logoColor=white)
![RAG](https://img.shields.io/badge/RAG-7a5c8c?style=flat-square&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-7a5c8c?style=flat-square&logo=scikitlearn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-7a5c8c?style=flat-square&logo=opencv&logoColor=white)
 
### Full-Stack & APIs
 
![React](https://img.shields.io/badge/React-5c7a5c?style=flat-square&logo=react&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-5c7a5c?style=flat-square&logo=nextdotjs&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-5c7a5c?style=flat-square&logo=tailwindcss&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-5c7a5c?style=flat-square&logo=fastapi&logoColor=white)
![Django REST](https://img.shields.io/badge/Django_REST-5c7a5c?style=flat-square&logo=django&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-5c7a5c?style=flat-square&logo=flask&logoColor=white)
![REST APIs](https://img.shields.io/badge/REST_APIs-5c7a5c?style=flat-square&logoColor=white)
![WebSockets](https://img.shields.io/badge/WebSockets-5c7a5c?style=flat-square&logoColor=white)
 
### Data & Cloud
 
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-8c6b3d?style=flat-square&logo=postgresql&logoColor=white)
![Redis Streams](https://img.shields.io/badge/Redis_Streams-8c6b3d?style=flat-square&logo=redis&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-8c6b3d?style=flat-square&logo=snowflake&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-8c6b3d?style=flat-square&logo=apachespark&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_(S3%2C_RDS%2C_Elastic_Beanstalk)-8c6b3d?style=flat-square&logo=amazonwebservices&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-8c6b3d?style=flat-square&logo=docker&logoColor=white)
 
### Tools & Practices
 
![Git](https://img.shields.io/badge/Git-6c757d?style=flat-square&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions_(CI%2FCD)-6c757d?style=flat-square&logo=githubactions&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-6c757d?style=flat-square&logo=pytest&logoColor=white)
![Code Reviews](https://img.shields.io/badge/Code_Reviews-6c757d?style=flat-square&logoColor=white)
![Agile](https://img.shields.io/badge/Agile-6c757d?style=flat-square&logoColor=white)
 
### Core CS
 
Data Structures & Algorithms • Object-Oriented Programming • Operating Systems • Concurrency • Distributed Systems
 
---
 
<div align="center">
### 💡 Always Learning. Always Building.
 
Debugging to root cause, shipping with tests, and building systems that hold up.
 
**📩 Let's Connect**
 
**Email:** <a href="mailto:shubdc1806@gmail.com">shubdc1806@gmail.com</a> • **Portfolio:** <a href="https://shubhojyoti-portfolio.vercel.app">shubhojyoti-portfolio.vercel.app</a>
 
</div>
 
