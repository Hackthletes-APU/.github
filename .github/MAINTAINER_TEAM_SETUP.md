# Maintainers team setup guide

Follow these steps once as an **organisation owner** to activate `@Hackthletes-APU/maintainers` for CODEOWNERS and review routing.

## Option A — GitHub website (recommended)

1. Open [github.com/orgs/Hackthletes-APU/teams](https://github.com/orgs/Hackthletes-APU/teams)
2. Click **New team**
3. Set:
   - **Team name:** `maintainers`
   - **Description:** `Core reviewers and community leads for APU Hackthletes`
   - **Visibility:** Visible (recommended for open source)
4. Click **Create team**
5. Add members (suggested initial list from [MAINTAINERS.md](../MAINTAINERS.md)):
   - `cindyyy11`
   - `JohnsonChin1009`
   - `raykon1221`
6. Go to **Organisation settings → Member privileges → Base permissions** and confirm members can create repositories if needed
7. For each project repository, optionally set:
   - **Settings → Collaborators and teams → Add team `maintainers`**
   - Role: **Maintain** or **Write** (Maintain is recommended for reviewers)

## Option B — GitHub CLI

Install [GitHub CLI](https://cli.github.com/) and authenticate as an org owner:

```powershell
gh auth login
gh api -X POST orgs/Hackthletes-APU/teams -f name=maintainers -f description="Core reviewers and community leads for APU Hackthletes" -f privacy=closed
gh api -X PUT orgs/Hackthletes-APU/teams/maintainers/memberships/cindyyy11 -f role=maintainer
gh api -X PUT orgs/Hackthletes-APU/teams/maintainers/memberships/JohnsonChin1009 -f role=maintainer
gh api -X PUT orgs/Hackthletes-APU/teams/maintainers/memberships/raykon1221 -f role=maintainer
```

## Verify it works

1. Open any org repository and create a test pull request
2. Confirm `@Hackthletes-APU/maintainers` is requested for review (from CODEOWNERS)
3. Open **Organisation → People → Teams** and confirm `maintainers` appears

## Optional org settings

| Setting | Location | Recommendation |
| --- | --- | --- |
| Pinned repositories | Org profile page | Pin `.github`, top projects, and Hacker Hub when live |
| Org description | Org settings → Profile | `Student-led hackathon & open-source community at Asia Pacific University` |
| Location | Org settings → Profile | `Kuala Lumpur, Malaysia` |
| Discussion | Repo or org settings | Enable for contribution questions |

## Update this list

When maintainers change, update [MAINTAINERS.md](../MAINTAINERS.md) and the profile README team section in the same pull request.
