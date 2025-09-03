# SIT223 / SIT753 – Task 8.1C: CI & DevSecOps with Jenkins

This repo (SIT223--Task-8.1C) holds my written artefacts and links.  
**Code for the DevSecOps pipeline runs in:**  
➡️ https://github.com/Tsunami281/8.2CDevSecOps.git

## Part 1 – Task 1 (GitHub Integration with Jenkins)
- Jenkins job polls GitHub for changes (no webhook required).
- Theoretical 7-stage pipeline (design only):
  1) Build – e.g., Maven/Gradle  
  2) Unit & Integration Tests – e.g., JUnit/Mocha  
  3) Code Analysis – e.g., SonarQube/ESLint  
  4) Security Scan – e.g., OWASP Dependency-Check/Snyk  
  5) Deploy to Staging – e.g., AWS EC2  
  6) Integration Tests on Staging  
  7) Deploy to Production  
(Designing stages/tools is required; no need to run this pipeline here.) :contentReference[oaicite:1]{index=1}

## Part 1 – Task 2 (DevSecOps Basics with npm)
Working repo: https://github.com/Tsunami281/8.2CDevSecOps.git

**Jenkins pipeline stages used:**
- Checkout  
- Install Dependencies (`npm install`)  
- Run Tests (`npm test || true`)  
- Generate Coverage (`npm run coverage || true`)  
- NPM Audit (`npm audit || true`)  
(Windows agents: use `bat` and `|| exit /b 0`.) :contentReference[oaicite:2]{index=2}

**Setup steps I followed:**
```bash
git clone https://github.com/snyk-labs/nodejs-goof.git
cd nodejs-goof
git remote remove origin
git remote add origin https://github.com/Tsunami281/8.2CDevSecOps.git
git push -u origin main
