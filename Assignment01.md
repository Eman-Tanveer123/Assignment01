

 Assignment 01: Git, Gitea, GitHub, Git LFS, and GitHub Pages
Summary
This solution report documents the complete practical execution of Assignment 01 for Cloud Computing. The lab work demonstrates essential DevOps and Cloud infrastructure concepts, including containerized service hosting, multi-remote Git management, binary large object handling with Git LFS, and public static web hosting via GitHub Pages.
Task 1: Self-Hosted Gitea Service Setup
1.1Concepts
•	What is Gitea? Gitea is a fast, lightweight, self-hosted Git service (similar to GitHub). Hosting it on an Ubuntu server provides full control over private repositories and code infrastructure.
•	Why Docker Compose? Docker Compose allows us to define and run multi-container Docker applications easily using a docker-compose.yml file. It ensures the Gitea container runs consistently without manual dependencies.
1.2 Step-by-Step Procedure
1.	Created a dedicated working directory ~/gitea on the Ubuntu server.
2.	Configured docker-compose.yml specifying the Gitea image, port mappings (3000:3000 for Web UI, 2222:22 for SSH), and volume storage.
3.	Started the container using docker compose up -d and confirmed container health.
4.	Accessed http://localhost:3000, completed initial admin configuration, and created the public repository Assignment01.
5.	Pushed initial project files from the Ubuntu server to Gitea.
Screenshots:-
1. Gitea Container Status
•	Filename: task1_gitea_running.png
•	What to show: Terminal screen running docker ps showing the active Gitea container and exposed port 3000.
 
2. Initial Gitea Push Output
•	Filename: task1_gitea_push.png
•	What to show: Terminal screen showing the successful git push output to the Gitea remote URL.
 
3. Gitea Web Repository
•	Filename: task1_gitea_repository.png
•	What to show: Browser window showing the Gitea web interface with the Assignment01 repository page and files.
 

Task 2: Multi-Remote Repository Management
2.1Concepts
•	What are Git Remotes? A Git remote is a common repository stored on a server. Git allows adding multiple remotes to a single local repository.
•	Why Dual Remotes? Setting up dual remotes (origin for local Gitea and github for GitHub) allows a developer to sync code across private on-premise servers and public cloud platforms using unified Git commands.
2.2 Step-by-Step Procedure
1.	Configured global Git identity (user.name and user.email) on the Ubuntu server.
2.	Initialized the local repository in ~/CC/Assignments/Assignment01.
3.	Added the primary Gitea remote (origin) and secondary GitHub remote (github) using git remote add.
4.	Staged, committed, and pushed changes to both Gitea and GitHub remotes using personal access tokens.
Screenshots:- 
4. Remote Configuration Verification
•	Filename: task2_remotes.png
•	What to show: Terminal output of git remote -v displaying both origin (Gitea) and github (GitHub) URLs.
 
5. GitHub Push Output
•	Filename: task2_github_push.png
•	What to show: Terminal output showing successful git push github main command execution.
 
6. GitHub Web Repository
•	Filename: task2_github_repository.png
•	What to show: Browser page showing your GitHub Assignment01 public repository with pushed files visible.
 
Task 3: Git Large File Storage (Git LFS)
3.1Concepts
•	The Large File Problem: Regular Git is designed for text source code. Tracking large binary files directly bloats repository history and causes slow download/upload performance.
•	How Git LFS Works: Git LFS replaces large files inside the Git repository with tiny pointer files. The actual heavy binary data is stored on a separate LFS server, keeping your Git repository fast and lightweight.
3.2 Step-by-Step Procedure
1.	Installed git-lfs on Ubuntu and initialized it using git lfs install.
2.	Configured tracking rules for specific large extensions or file names using git lfs track.
3.	Verified tracking configuration saved inside the .gitattributes file.
4.	Added 3 large binary files, committed them, and verified LFS tracking status.
5.	Pushed the repository including LFS binary pointers to the remotes.
Screenshots:- 
7. Git LFS Initialization & Tracking
•	Filename: task3_lfs_setup.png
•	What to show: Terminal screen showing git lfs install, git lfs track commands, and the contents of .gitattributes.
 
8. Tracked LFS Binary Files
•	Filename: task3_lfs_files.png
•	What to show: Terminal output of git lfs ls-files displaying the three large files tracked by LFS along with their hashes.
 
9. Git LFS Push Output
•	Filename: task3_lfs_push.png
•	What to show: Terminal screen showing git push output uploading Git LFS objects.
 
Task 4: Portfolio Deployment via GitHub Pages
4.1Concepts
•	What is GitHub Pages? GitHub Pages is a static web hosting service that serves HTML, CSS, and JavaScript files directly from a GitHub repository to the public internet.
•	User Page Convention: By naming the repository <username>.github.io, GitHub automatically publishes the website live at https://<username>.github.io/.
4.2 Step-by-Step Procedure
1.	Created a public repository named eman-tanveer123.github.io.
2.	Developed portfolio web files (index.html and styles.css) containing About Me, Education, Skills, and Projects sections.
3.	Pushed the portfolio code to the main branch.
4.	Verified deployment under Repository Settings $\rightarrow$ Pages.
5.	Loaded and verified the active live site at https://eman-tanveer123.github.io/.
Screenshots:-
10. Portfolio Source Repository
•	Filename: task4_pages_repository.png
•	What to show: Browser window showing the eman-tanveer123.github.io repository on GitHub with index.html and styles.css.
 
11. GitHub Pages Deployment Status
•	Filename: task4_pages_deployment.png
•	What to show: Browser page of Repository Settings $\rightarrow$ Pages showing "Your site is live at https://eman-tanveer123.github.io/".
 
12. Live Portfolio Verification
•	Filename: task4_portfolio_live.png
•	What to show: Browser page of the active website at https://eman-tanveer123.github.io/ displaying full sections (About Me, Education, Skills, Projects).
 

