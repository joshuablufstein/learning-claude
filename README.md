# learning-claude

A mini course on Claude and large language models, built for non-engineers. Live at https://joshuablufstein.github.io/learning-claude/.

## What this is

A single self-contained HTML page (`index.html`) that lists ~28 hours of free resources arranged in four phases. No build step, no dependencies, no JavaScript. Edit the file, push, GitHub Pages redeploys automatically.

## Updating

```bash
cd "~/Desktop/Claude Playground/learning-claude"
# edit index.html
git add index.html
git commit -m "describe the change"
git push
```

The auto-push hook in `~/.git/hooks/post-commit` does not apply here — this repo lives in its own folder, so a manual `git push` is needed after each commit.

## Adding a new resource

Every link on the page must resolve. Before adding one:

```bash
curl -s -L -o /dev/null -w "%{http_code}\n" "URL_HERE"
```

Must return `200`. For YouTube videos, use the oEmbed check:

```bash
curl -s -o /dev/null -w "%{http_code}\n" "https://www.youtube.com/oembed?url=YOUTUBE_URL&format=json"
```

Also `200` if the video exists.
