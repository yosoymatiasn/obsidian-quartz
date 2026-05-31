---
unlisted: "true"
---
# Quartz Cheat Sheet

## Architecture

    Private Vault
    └── 90 Public/
        ├── index.md

    Quartz
    └── content -> 90 Public (symlink)

Anything inside `90 Public/` becomes publishable.

## Start Local Server

From Quartz root:

    npx quartz build --serve

Open:

    http://localhost:8080

Quartz automatically rebuilds when files change.

## Internal Links

Link notes exactly like Obsidian:

    [[Climbing Lingo]]
    [[Spanish/Climbing Vocabulary]]

Quartz automatically resolves links.

## Images

Recommended structure:

    90 Public/
    ├── assets/
    │   ├── duck.jpeg
    │   └── squirrel.jpeg
    └── Nature Walk.md

## Folder Structure

    90 Public/
    ├── index.md
    ├── Climbing/
    │   ├── Climbing Lingo.md
    │   └── Training.md
    ├── Spanish/
    │   ├── Coffee Vocabulary.md
    │   └── Climbing Vocabulary.md
    └── NYC/

Folders become site sections.

## Frontmatter (Optional)

    ---
    title: Climbing Lingo
    tags:
      - climbing
      - spanish
    ---

Useful for search and organization.

## Common Problems

### Images show 404

Terminal:

    [404] /image.jpeg

Fix:

- Put image inside `90 Public/`
- Link using correct path:

    ![[assets/image.jpeg]]

### Note shows but links 404

Check:
	[[Exact note name]]

Quartz matches note names.

### Changes not updating

Restart:

    Ctrl+C
    npx quartz build --serve

## Publish to GitHub

Commit changes:

    git add .
    git commit -m "Update notes"
    git push

GitHub Actions deploys site automatically.