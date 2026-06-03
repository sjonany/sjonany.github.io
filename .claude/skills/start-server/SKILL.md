---
name: start-server
description: Start the local Jekyll dev server for this blog (sjonany.github.io) with live reload, so changes to writing.md, posts, tags, and includes can be previewed in a browser. Use when the user says "start the server", "serve the site", "preview the blog locally", or asks to run/view the site.
---

# Start the local Jekyll server

Serve this site locally with live reload at **http://localhost:4000**.

## Steps

1. Run the server from the repo root, in the **background** (it is long-running).
   The `GEM_HOME`/`PATH` exports are required because gems are installed under
   `~/.gems` (not system-wide):

   ```bash
   cd ~/Code/personal/sjonany.github.io
   export GEM_HOME="$HOME/.gems"; export PATH="$HOME/.gems/bin:$PATH"
   bundle exec jekyll serve --livereload
   ```

2. Tell the user it's running at **http://localhost:4000/** (the writing page is
   `http://localhost:4000/writing.html`). With `--livereload`, edits rebuild
   automatically — just refresh the browser.

3. To stop it, the user presses Ctrl+C in that terminal, or you stop the
   background job.

## Notes

- If `bundle: command not found` or a gem is missing, run `bundle install` first
  (same `GEM_HOME`/`PATH` exports), then retry.
- `_config.yml` and `Gemfile` are local-only (gitignored); they reproduce the
  GitHub Pages build so the local preview matches production.
- For a one-off build without serving (e.g. to verify it compiles), use
  `bundle exec jekyll build` instead.
