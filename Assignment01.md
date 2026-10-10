# Cloud Computing - Assignment 01 Report

**Student Name:** Eman Tanveer  
**Course:** Cloud Computing  
**Assignment:** 01 (Git, Gitea, GitHub, Git LFS, and GitHub Pages)

---

## Task 1: Self-Hosted Gitea Service Setup

### 1.1 Concepts
* **What is Gitea?** Gitea is a fast, lightweight, self-hosted Git service that provides full control over private repositories and code infrastructure.
* **Why Docker Compose?** Docker Compose allows us to define and run multi-container applications using a single configuration file, ensuring consistent execution without manual dependencies.

### 1.2 Step-by-Step Procedure
1. Created a dedicated working directory `~/gitea` on the Ubuntu server.
2. Configured `docker-compose.yml` specifying the Gitea image and port mappings (`3000:3000` for Web UI, `2222:22` for SSH).
3. Started the container using `docker compose up -d` and confirmed container health.
4. Accessed `http://localhost:3000`, completed initial admin setup, and created repository `Assignment01`.
5. Pushed initial project files from Ubuntu server to Gitea.

### 1.3 Screenshots
![Gitea Container Status](task1_gitea_running.png)
![Initial Gitea Push Output](task1_gitea_push.png)
![Gitea Web Repository](task1_gitea_repository.png)

---

## Task 2: Multi-Remote Repository Management

### 2.1 Concepts
* **What are Git Remotes?** Remotes are references to hosted versions of a repository on external servers.
* **Why Dual Remotes?** Configuring dual remotes (`origin` for local Gitea and `github` for GitHub) allows seamless synchronization across private/on-premise servers and public cloud platforms.

### 2.2 Step-by-Step Procedure
1. Set up Git identity (`user.name` and `user.email`) on Ubuntu.
2. Created public repository `Assignment01` on GitHub.
3. Added GitHub remote using `git remote add github <URL>`.
4. Verified remote endpoints using `git remote -v`.
5. Pushed all branches and commit history to GitHub via `git push github main`.

### 2.3 Screenshots
![Git Remotes Configuration](task2_remotes.png)
![GitHub Push Output](task2_github_push.png)
![GitHub Web Repository](task2_github_repository.png)

---

## Task 3: Git LFS Configuration & Binary Artifact Management

### 3.1 Concepts
* **Why Git LFS?** Git is designed for text/code; storing large binary files directly bloats repository size. Git LFS replaces large files with tiny pointer files, storing binary content separately.
* **Storage Allocation:** Small text files stay inside the repository, while large binary files (`.bin`, `.zip`, `.psd`) are routed to LFS storage.

### 3.2 Step-by-Step Procedure
1. Installed Git LFS on Ubuntu server using `git lfs install`.
2. Tracked large binary pattern using `git lfs track "*.bin"`.
3. Verified generation of `.gitattributes` file.
4. Created three test dummy files (`large-file-1.bin`, `large-file-2.bin`, `large-file-3.bin`).
5. Staged, committed, and pushed binary files to GitHub LFS storage.

### 3.3 Screenshots
![Git LFS Setup](task3_lfs_setup.png)
![LFS Tracked Files List](task3_lfs_files.png)
![LFS Push Log Output](task3_lfs_push.png)

---

## Task 4: GitHub Pages Portfolio Deployment

### 4.1 Concepts
* **What is GitHub Pages?** A static site hosting service that takes HTML, CSS, and JavaScript files directly from a repository and publishes a live website.
* **Use Case:** Ideal for developer portfolios, documentation, and project showcases.

### 4.2 Step-by-Step Procedure
1. Created user site repository named `Eman-Tanveer123.github.io`.
2. Added clean HTML/CSS responsive portfolio landing page (`index.html`).
3. Enabled GitHub Pages under **Settings -> Pages** selecting `main` branch.
4. Verified successful build and live site accessibility.

### 4.3 Screenshots
![Pages Repository Structure](task4_pages_repository.png)
![GitHub Pages Deployment Status](task4_pages_deployment.png)
![Live Portfolio Website](task4_portfolio_live.png)

---

## Submission Links
* **Gitea Local Repository:** `http://localhost:3000/Eman-Tanveer123/Assignment01`
* **GitHub Main Repository:** `https://github.com/Eman-Tanveer123/Assignment01`
* **Live Portfolio Website:** `https://eman-tanveer123.github.io/`
