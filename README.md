# Mein privater Vault

## What You Need

1. Create a GitHub repository (if you haven't already)
2. Create a personal access token (classic) under settings and select "repo" scope (remember to save it somewhere secure)
3. Install Obsidian community plugin "Git"

## Set Up with Terminal

**→ Terminal commands for Linux/MacOS.**

### Push a Directory to GitHub

1. Go to the direct‘ory you want to push: `cd <VAULT_PATH>`
    - Example: `cd Documents/vault`
2. Initialize Github (main branch usually called "main"): `git init --initial-branch=main`
3. Add your Git repository (remote name usually "origin") and add the URL in this format: `git remote add origin https://<PERSONAL_ACCESS_TOKEN>@github.com/<USERNAME>/<REPO>.git`
    - Example URL: `https://ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX@github.com/joshua/my-notes.git`
4. Download history: `git fetch origin`
5. Include everything: `git add .`
6. Commit with a message ("init" for initial push): `git commit -m "init"`
7. Push changes (**Warning: Will overwrite entire repository!**): `git push -f`

### Clone a Repository from GitHub

1. Remove everything from vault directory (in case the folder isn't empty)
    - Delete everything in this directory (**Warning: Will delete absolutely everything inside this folder!**): `rm -rf <PATH>/{.??,}*`
        - Example: `rm -rf Documents/vault/{.??,}*`
    - Safer option that doesn't involve deleting
        - Create new directory (in Documents): `mkdir -p <DESTINATION_PATH>`
            - Example: `mkdir -p Documents/backup`
        - Move everything to this folder: `mv <VAULT_PATH>/{.??,}* <DESTINATION_PATH>`
            - Example: `mv Documents/vault/{.??,}* Documents/backup`
2. Clone a repository `git clone https://<PERSONAL_ACCESS_TOKEN>@github.com/<USERNAME>/<REPO>.git <VAULT_PATH>`
    - Example URL: `https://ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX@github.com/joshua/vault.git Documents/dir`

## Set Up Using Command Palette

**→ Built in command palette (Ctrl/CMD + P) that works on every system.**

https://linked-blog-starter.vercel.app/connect-obsidian-vault-with-github

_You can only clone to a subfolder, otherwise it would overwrite the Git plugin._

## Garbage Collection

To keep the .git directory size to a minimum and maintain fast loading times, run `git gc` every now and then.

This will run garbage collection, cleaning the local clone.

Alternatively : `git gc --aggressive --prune=now`
