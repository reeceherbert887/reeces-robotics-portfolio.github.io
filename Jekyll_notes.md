# Jekyll Course/Society Page Fix Notes

## What was going wrong

Do not edit files inside `_site/`.

`_site/` is Jekyll's generated output folder. Every time you run Jekyll, it rebuilds this folder from the source files and overwrites anything inside it. Git also ignores `_site/`, so changes inside `_site/` will not commit.

The files you should edit are:

- `course-projects.md`
- `society-projects.md`
- `_course-projects/...`
- `_society-projects/...`

## What I fixed

- Updated `course-projects.md` with the fuller course dropdown content.
- Updated `society-projects.md` so the Pepper section appears on the Society Projects page.
- Added proper Jekyll front matter to the Pepper markdown files.
- Added stable permalinks for:
  - `/society-projects/pepper/pepper-dance/`
  - `/society-projects/pepper/pepper-refreshers/`
  - `/society-projects/pepper/pepper-robo-grad/`

## Correct commands

```bash
git status

git add course-projects.md society-projects.md _society-projects/pepper/*.md

git commit -m "Fix course and society project pages"

git push
```

## Important

If a page disappears after running Jekyll, it usually means you edited the generated HTML inside `_site/` instead of the real source markdown file.
