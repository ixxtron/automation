# GitHub Actions Workflows - Intro
GitHub Actions workflows for Continuous Integration and automation pipelines/solutions
## Getting Started
---
**What will be covered during this session?** \
This lesson is intended for anyone who's getting getting started for the first time or needs to started with GitHub Actions \

**Before getting started...** 
You mus have a github account
### Working with GitHub Workflow (Starters)
To get started select the type of workflow from github GitHub Actions: Starters 
- [Continuous Integration Based Workflows](https://github.com/actions/starter-workflows)
- [Automation Based Workflows](https://github.com/actions/starter-workflows/tree/main/automation)

# Adding a GitHub Actions Workflow
To an existing repo ( < 5 minutes)
---
1. From your repository on GitHub, create a new file in the `.github/workflows` directory named `superlinter.yml`
2. Copy the following `YAML` contents into the `superlinter.yml` file. Note: If your default branch is not main, update \ 
the value of `DEFAULT_BRANCH` to match your repository's default branch name.
`name: Super-Linter`

**Run this workflow every time a new commit pushed to your repository on: `push`**
```
jobs:
  # Set the job key. The key is displayed as the job name
  # when a job name is not provided
  super-lint:
    # Name the Job
    name: Lint code base
    # Set the type of machine to run on
    runs-on: ubuntu-latest

    steps:
      # Checks out a copy of your repository on the ubuntu-latest machine
      - name: Checkout code
        uses: actions/checkout@v2

      # Runs the Super-Linter action
      - name: Run Super-Linter
        uses: github/super-linter@v3
        env:
          DEFAULT_BRANCH: main
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
 ```
To run your workflow, scroll to the bottom of the page and select Create a new branch for this commit and start a pull request. Then, to create a `pull request`, click `Propose new file`.

### Used Sources
- https://docs.github.com/en/free-pro-team@latest/actions/quickstart
- https://github.com/actions/starter-workflows
- https://github.com/actions/starter-workflows/tree/main/automation

---
### Related Sources & Resources
[Introduction to GitHub Actions : my website build & deployment](https://www.youtube.com/watch?reload=9&v=rgxbeIvQj0Q)



          

