# Auto-Contributor Access Pipeline 🚀
Automate contributor onboarding: A Google Form collects user info → Zapier pushes it to your GitHub repo → A GitHub Actions workflow triggers and grants repo access using your provided Personal Access Token (PAT).

**Key Benefits**:
- Zero manual invites for contributors
- Secure, auditable access granting
- Integrates seamlessly with Google Workspace + GitHub

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Zapier](https://img.shields.io/badge/Zapier-FF4A00?style=for-the-badge&logo=zapier&logoColor=white)
![Google Forms](https://img.shields.io/badge/Google%20Forms-4285F4?style=for-the-badge&logo=google&logoColor=white)

## How It Works 🔄

1. **User submits** Google Form (e.g., GitHub username, reason for access).
2. **Zapier** detects new response → creates a file/commit in the repo (`quiz-results`).
3. **GitHub Workflow** triggers on push → parses the request → uses your PAT to add the user as collaborator to target repos.

High-level flow (text diagram):

```mermaid
graph LR
    A[Google Form Submission] --> B[Zapier Zap]
    B --> C[Create File/Commit in GitHub Repo]
    C --> D[GitHub Actions Workflow Trigger]
    D --> E[Parse Request]
    E --> F[GitHub API: Add Collaborator]
    F --> G[User Gains Access! 🎉]
