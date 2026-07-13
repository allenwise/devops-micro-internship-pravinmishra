# Assignment 4 — Building Your AI Team

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will build and configure a set of specialized AI subagents inside your project. You will learn how different models and tool permissions define agent behavior, and you will trigger two real agent delegations to analyze security and cost aspects of your Terraform infrastructure.

---

# Task 1 — Create the Agents Folder and Add Files

## Goal

Create the `.claude/agents/` directory and add all required agent files.

### Evidence

#### Screenshot 1 — Agents folder structure in VS Code

![Subagent created](Screenshot from 2026-07-10 20-43-16.png0 20-03-23.png>)

# Task 2 — Compare the Agent Configurations

## Goal

Analyze the configuration differences between the three agents and demonstrate understanding of model and tool selection.

### Written Answers

#### 1. Why does the cost optimizer use Haiku instead of Sonnet?

- Haiku is typically chosen for tasks that require speed and efficiency over depth. Cost optimization often involves scanning large datasets, running quick heuristics, and producing lightweight recommendations.
- Sonnet, on the other hand, is more resource-intensive and tuned for nuanced reasoning. For cost optimization, that   extra depth isn’t always necessary — the priority is fast, scalable analysis

#### 2. Why does the security auditor NOT have Write in its tools list?

Security auditor roles are designed to be read-only by principle. They inspect, verify, and flag issues but should not alter configurations directly.
Removing “Write” ensures separation of duties: auditors can’t accidentally or maliciously change what they’re meant to review. This enforces compliance and prevents conflicts of interest.

#### 3. Why does the tf-writer use `inherit` instead of a specific model?

The tf-writer is often a utility that generates Terraform files or infrastructure-as-code templates.
By using inherit, it ensures consistency with the parent workflow’s model choice. This avoids mismatches where the writer might generate code based on a different reasoning engine than the one used to plan or validate infrastructure.
It’s essentially a safeguard: the writer inherits the model context so outputs align with the rest of the pipeline.

### Evidence

#### Screenshot 2 — security-auditor.md frontmatter

![Security Snap](<Model for security.jpg>)

#### Screenshot 3 — cost-optimizer.md frontmatter

![cost snap](<Cost Model.jpg>)

# Task 3 — Run the Security Auditor

## Goal

Trigger the security auditor agent and analyze the generated security report for your Terraform infrastructure.

### Evidence

#### Screenshot 4 — Security auditor delegation triggered

![Triggered Report](<Screenshot from 2026-07-10 21-13-20.png>)

#### Screenshot 5 — Security audit report output

![Audit Report](<Screenshot from 2026-07-10 21-14-33.png>)

# Task 4 — Run the Cost Optimizer

## Goal

Trigger the cost optimizer agent and review the generated cost optimization report.

### Evidence

#### Screenshot 6 — Cost optimization report output

Add your screenshot here.

---

# Submission Instructions

- Ensure all agent files are committed in `.claude/agents/`
- Complete all written answers in your Google Doc submission
- Push final changes to your forked GitHub repository
- Submit only the Google Doc link as required

---

## Google Doc Link

Paste your Google Doc URL here:

https://docs.google.com/document/d/1HuYFJTghDIxCxSJ9Sl0Ucfn9ckrkH4HbUpUsSu82HHA/edit?usp=sharing

## GitHub Repository URL

Paste your forked repository URL here:

https://github.com/allenwise/Ultimate-Agentic-DevOps-with-Claude-Code

# Completion Checklist

- [ ] `.claude/agents/` folder contains all 3 agent files
- [ ] Screenshot 2 shows correct `security-auditor.md` configuration
- [ ] Screenshot 3 shows correct `cost-optimizer.md` configuration
- [ ] All 3 written answers completed in Google Doc
- [ ] Security auditor executed successfully
- [ ] Cost optimizer executed successfully
- [ ] Security report is visible with findings
- [ ] Cost report is visible with recommendations
- [ ] All required screenshots added
- [ ] GitHub repo updated with agents

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://pravinmishra.com/dmi  
- 🎓 DevOps for Beginners (Udemy): https://www.udemy.com/course/devops-for-beginners-docker-k8s-cloud-cicd-4-projects/  
- 🎓 Agentic AI DevOps with Claude Code: https://www.udemy.com/course/ultimate-agentic-ai-devops-with-claude-code/  
- 🎓 DevOps with Claude Code: Terraform, EKS, ArgoCD & Helm: https://www.udemy.com/course/devops-with-claude-code-terraform-eks-argocd-helm/  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*