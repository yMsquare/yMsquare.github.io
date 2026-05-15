# Quartz + GitHub Pages Deployment

This repository is ready for GitHub Pages deployment with GitHub Actions.

## 1. Create your GitHub repository

Create a new repository on GitHub. Either of these works:

- `YOUR_GITHUB_USERNAME.github.io`
- any normal repository name such as `garden` or `portfolio`

If you use a normal repository name, your site URL will be:

`https://YOUR_GITHUB_USERNAME.github.io/YOUR_REPOSITORY_NAME`

## 2. Update `baseUrl`

Edit [quartz.config.ts](/Users/msquare/Documents/Codex/2026-05-07/new-chat-4/quartz.config.ts) and replace:

`YOUR_GITHUB_USERNAME.github.io/YOUR_REPOSITORY_NAME`

Examples:

- user site: `octocat.github.io`
- project site: `octocat.github.io/garden`

Do not include `https://`.

## 3. Point this local repo to your own GitHub repo

Run:

```bash
git remote remove origin
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME.git
```

## 4. Commit and push

```bash
git add .
git commit -m "Set up Quartz site"
git branch -M main
git push -u origin main
```

## 5. Enable GitHub Pages

On GitHub:

1. Open your repository.
2. Go to `Settings` -> `Pages`.
3. Under `Build and deployment`, set `Source` to `GitHub Actions`.

After that, every push to `main` will rebuild and redeploy the site.

## 6. Optional local preview

If local npm permissions are clean, use:

```bash
npm install
npx quartz build --serve
```
