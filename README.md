# Spin Coupling Visualiser

An interactive 3-D visualiser of quantum spin coupling (Clebsch–Gordan fusion).
Two spin coherent states **ψ_v**, **ψ_w** are shown as vectors on their Bloch
spheres, and the coupled states **ψ⁽ᶜ⁾** they produce under the fusion rule
*V_a ⊗ V_b ≅ ⊕_c V_c* (for *c ∈ {|a−b|, …, a+b}*) are rendered live as Husimi
densities on the nested output spheres. Change the angle between the vectors and
everything — channel amplitudes, peak construction, cross-sections — updates
instantly.

It is a single, self-contained HTML file (Three.js + jsPDF loaded from a CDN).
No build step, no dependencies to install.

## Live demo

**https://martiensventer.github.io/spin-coupling-visualiser/**

> If that link 404s, check that the GitHub username in the URL matches your
> account and that Pages is enabled (see *Hosting* below).

## What it shows

- **Input spheres** — the two coherent states *v* (|v| = a⁄2) and *w* (|w| = b⁄2)
  as vectors from the sphere centre; optional density shading, radii (j-values),
  and the angle γ = ∠(v, w).
- **Coupled states** — each allowed channel *V_c* as a spin-coherent (Husimi)
  density, its channel amplitude λ⁽ᶜ⁾ and probability P = λ².
- **Peak construction** — where each coupled density peaks, built geometrically
  from v and w (the parallelograms, bisector and triangle of the construction),
  shown in the cross-section and focused views. Near antiparallel the peak
  degenerates to a ring, which phases in as γ → 180°.
- **Three views** — *All states*, *Cross-section* (a cut along the rotating
  v,w plane), and *Focused* on a single channel.

## Controls

- Set spins a, b and the two vectors' latitude/longitude.
- Toggle spheres, vectors, contours, construction lines, parallel-line markers,
  and the v+w ray.
- Switch angle units between degrees and radians (radians shown as fractions of π).
- **Export** any view (input / output / both) as **PDF** (fixed 1920×1080 page)
  or **PNG** (natural panel size).

## Run locally

Just open `index.html` in a modern browser. A CDN connection is needed for
Three.js and jsPDF. To serve it locally instead:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Hosting (GitHub Pages)

The repo is a single `index.html`, so Pages serves it directly:

1. Repository **Settings → Pages**.
2. **Source:** *Deploy from a branch*; **Branch:** `main`, **Folder:** `/ (root)`.
3. Save. The site goes live at
   `https://<your-username>.github.io/spin-coupling-visualiser/` within a minute.

## Tech

- [Three.js](https://threejs.org/) r128 for the 3-D rendering.
- [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 for PDF export.
- Plain HTML/CSS/JS — one file, no bundler.

## License

[MIT](LICENSE).
