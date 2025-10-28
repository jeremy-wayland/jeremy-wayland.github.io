# My Personal Website

## Theme as a Git submodule

This site uses my custom Hugo theme as a Git submodule at `themes/custom-hugo-theme`.

- Repo: git@github.com:jeremy-wayland/custom-hugo-theme.git
- Branch tracked: `main`

### Clone with submodules

```bash
git clone --recurse-submodules git@github.com:jeremy-wayland/jeremy-wayland.github.io.git
```

If you already cloned without submodules:

```bash
git submodule update --init --recursive
```

### Keep the theme up to date

Fetch the latest commit on the tracked branch (`main`) and update the submodule pointer:

```bash
git submodule update --remote --merge themes/custom-hugo-theme
git add themes/custom-hugo-theme
git commit -m "chore(theme): update custom-hugo-theme to latest main"
```

Alternatively, rebase instead of merge:

```bash
git submodule update --remote --rebase themes/custom-hugo-theme
```

### Pulling changes (repo + submodules)

```bash
git pull --recurse-submodules
git submodule update --init --recursive
```

### Notes

- The submodule URL is SSH-based for contributor convenience. If you prefer HTTPS, change it in `.gitmodules` and run `git submodule sync --recursive`.
- Hugo is configured to use the theme via `theme = "custom-hugo-theme"` in `hugo.toml`.
