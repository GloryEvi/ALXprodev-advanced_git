# ALXprodev-advanced_git

This repository demonstrates advanced Git workflows using GitFlow.
## GitFlow Workflow Commands

### Task 1: Initialize GitFlow Workflow
```bash
# Install git-flow (Ubuntu)
sudo apt-get install git-flow

# Verify installation
git flow version

# Clone repository
git clone https://github.com/yourusername/ALXprodev-advanced_git.git
cd ALXprodev-advanced_git

# Create develop branch
git checkout -b develop

# Create initial commit
git commit --allow-empty -m "Initial empty commit"

# Push develop branch
git push -u origin develop

# Create main branch
git checkout -b main
git push -u origin main

# Switch back to develop
git checkout develop

# Initialize GitFlow
git flow init -d

# Create README.md
touch README.md

# Add content to README.md
echo "# ALXprodev-advanced_git" > README.md
echo "" >> README.md
echo "This repository demonstrates advanced Git workflows using GitFlow." >> README.md

# Commit and push
git add README.md
git commit -m "Add README.md file"
git push

2
# Create feature branch for login
git checkout develop
git flow feature start implement-login

# Create login-page directory and README
mkdir login-page
echo "Login Feature Coming soon" > login-page/README.md

# Commit and push feature
git add login-page/
git commit -m "feat: scaffolding login page"
git push origin feature/implement-login

3
# Create feature branch for signup
git checkout develop
git flow feature start implement-signup

# Create signup-page directory and README
mkdir signup-page
echo "feature coming soon" > signup-page/README.md

# Commit and push signup feature
git add signup-page/
git commit -m "feat: add signup page scaffolding"
git push origin feature/implement-signup

# Finish both feature branches (merge to develop)
git flow feature finish implement-signup
git flow feature finish implement-login

# Create release branch
git flow release start 1.0.0

# Add data requirements to signup README
echo " data requirements: email, firstName, lastName, profilePic]" >> signup-page/README.md

# Commit and push release changes
git add signup-page/README.md
git commit -m "docs: add data requirements to signup page"
git push origin release/1.0.0

# Finish release (merges to main and develop, creates tag)
git flow release finish 1.0.0

# Push tags and updated branches
git push --tags
git push origin main
git push origin develop
