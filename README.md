# syedfahadrizvi.github.io

Personal portfolio site for Syed Muhammad Fahad Rizvi — Senior Machine Learning Engineer
(computer vision, 3D reconstruction, multi-object tracking, MLOps). Static, hand-written
HTML/CSS with no build step, served via GitHub Pages.

## Structure

| Page | Path |
| --- | --- |
| Home / overview | `index.html` |
| Projects index | `projects.html` |
| Experience & education | `experience.html` |
| Label-Free Detector Training | `projects/label-free-detection.html` |
| Modular Neural Photogrammetry Pipeline | `projects/photogrammetry.html` |
| US DOT Intersection Safety Challenge | `projects/dot-challenge.html` |
| Vulnerable Road User Tracking | `projects/vru-tracking.html` |
| Automated Single-Camera Calibration | `projects/camera-calibration.html` |

- `styles.css` — shared stylesheet (light/dark aware, responsive, print styles).
- `assets/` — images (e.g. the photogrammetry comparison grid).

Project case-study content is derived from the LaTeX technical portfolio; pipeline diagrams
are reimplemented as CSS flow diagrams. To preview locally: `python3 -m http.server` and open
<http://localhost:8000>.
