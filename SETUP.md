# Kosala GitHub Profile — Ultimate README Setup

This package replaces the existing GitHub profile README with a longer, cleaner, and more reliable version.

## Problems corrected

1. **The Mermaid timeline was very small and showed extra diagram controls.**  
   It was replaced with `assets/journey-ultimate.svg`.

2. **The footer service rendered as a narrow coloured strip.**  
   It was replaced with `assets/footer-ultimate.svg`.

3. **The profile SVG was heavy.**  
   The embedded portrait was compressed while keeping the animated orbit design.

4. **The previous project section was too short.**  
   The new README contains detailed featured projects, case studies, a complete project catalogue, skills, workflow, architecture interests, and a roadmap.

5. **The layout depended too much on third-party graphics.**  
   The main banner, portrait, system-flow diagram, journey diagram, and footer are local SVG files.

6. **The contribution-snake workflow needed clearer triggering and concurrency control.**  
   The included workflow can run manually and every 12 hours.

## Required repository structure

```text
kosaladathapththu/
├── README.md
├── SETUP.md
├── assets/
│   ├── hero-ultimate.svg
│   ├── profile-orbit-ultimate.svg
│   ├── system-flow-ultimate.svg
│   ├── journey-ultimate.svg
│   └── footer-ultimate.svg
└── .github/
    └── workflows/
        └── snake.yml
```

## Upload steps

1. Open `kosaladathapththu/kosaladathapththu`.
2. Replace the current `README.md`.
3. Open the `assets` folder.
4. Upload all five SVG files from this package.
5. Replace `.github/workflows/snake.yml`.
6. Commit the changes to `main`.
7. Open the **Actions** tab.
8. Select **Generate Contribution Snake**.
9. Click **Run workflow**.
10. Wait for the workflow to finish.
11. Open the public GitHub profile and press `Ctrl + F5`.

## Important filename check

GitHub filenames are case-sensitive. These names must be exact:

```text
hero-ultimate.svg
profile-orbit-ultimate.svg
system-flow-ultimate.svg
journey-ultimate.svg
footer-ultimate.svg
```

Do not accidentally create this structure:

```text
assets/assets/hero-ultimate.svg
```

The SVG files must be directly inside the first `assets` folder.

## Expected result

- Animated full-width profile banner
- Animated portrait
- Animated system-integration diagram
- Long professional profile content
- Detailed internship and project sections
- GitHub statistics
- Contribution snake
- Animated developer journey
- Reliable local SVG footer
