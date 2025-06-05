# 🔐 GitHub Role Concept with Repository-Specific Teams

This document outlines the GitHub access control model for **drjve AG**, using **repository-specific Teams** as interfaces for managing user roles and responsibilities.

---

## 🎯 Purpose

To ensure secure, auditable, and well-scoped access to each GitHub repository by assigning contributors to role-based Teams that reflect their responsibilities.

---

## 📦 Team Naming Convention

Teams follow a structured naming pattern:

```
repo-<repo-name>-<role>
```

**Examples:**

- `repo-ml-pricing-admin`
- `repo-data-platform-contributor`
- `repo-ai-research-viewer`

---

## 🏗️ Standard Roles per Repository

Each repository should define up to four role-specific Teams:

| Team Name                     | Permissions | Description                                              |
|------------------------------|-------------|----------------------------------------------------------|
| `repo-<name>-admin`          | Admin       | Full control, including settings and branch protection   |
| `repo-<name>-maintainer`     | Maintain    | Workflow automation, code review, and config management  |
| `repo-<name>-contributor`    | Write       | Actively contributes code, data, or documentation        |
| `repo-<name>-viewer`         | Read/Triage | Read-only access or issue triage                         |

---

## 📂 Example: `ml-pricing-engine`

| Team                          | Permission | Purpose                             |
|------------------------------|------------|-------------------------------------|
| `repo-ml-pricing-admin`      | Admin      | Senior engineers, repo ownership    |
| `repo-ml-pricing-maintainer` | Maintain   | DevOps, reviewers, lead engineers   |
| `repo-ml-pricing-contributor`| Write      | Data scientists and ML developers   |
| `repo-ml-pricing-viewer`     | Read       | Stakeholders, QA, interns           |

---

## ✅ Best Practices

- Apply the **least privilege principle** — grant access only as needed.
- Enforce **branch protection rules** for critical branches (`main`, `release/*`).
- Use **CODEOWNERS** to define required reviewers by team.
- Assign users to **only one role team per repo** to avoid ambiguity.
- Reuse team definitions across projects where applicable.

---

## 🧰 Optional Enhancements

- Automate team and permission provisioning via:
  - GitHub CLI
  - Terraform with `integrations/github`
- Include team responsibilities in:
  - `README.md` under "Contributors"
  - `CONTRIBUTING.md` under "Access & Roles"
- Document team membership rotation and access audits quarterly.

---

## 📘 Related Resources

- [GitHub Teams Documentation](https://docs.github.com/en/organizations/collaborating-with-groups-in-your-organization/about-teams)
- [Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-protected-branches)
- [CODEOWNERS Syntax](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)

---
