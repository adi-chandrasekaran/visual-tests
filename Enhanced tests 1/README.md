# Enhanced tests 1

New, independent visualization experiments. Original prototypes and the combined application are not modified by these enhancements. Each module is delivered as its own PR for manual testing and merging before the next module starts.

## 01 — Radial phylogenetic lineage

Open `01-radial-lineage.html` in Cursor and run using your HTML preview workflow. No localhost server or build is needed. Internet access loads pinned D3.js 7.9.0.

The atlas displays 128 synthetic observed clones, four coloured lineage groups, internal ancestors, and three annotation rings (clone state, mutation burden, and sampling day). Labels, branch colours, and ring colours have distinct meanings. Branch radii show cumulative invented divergence values; dotted extensions align terminal annotations. Topology mode instead aligns the tips and does not encode branch lengths.

Try selecting a node, branch, label, or ring; inspecting an ancestral group; filtering by lineage; searching for `CL-A001` and pressing Enter; hiding labels/rings; rotating, zooming, panning, and resetting; and downloading an SVG. Selection highlights a subtree and its ancestry. Tab through nodes and use Enter or Space to inspect them. The SVG export retains annotations and includes the current rotation and filtering, with pan/zoom reset to fit the figure.

All topology, divergence, variants, dates, and state labels are deterministic invented demo data, not inferred or validated biology. No time or genetic-distance calibration is claimed.

References: [D3 cluster layout](https://d3js.org/d3-hierarchy/cluster), [D3 zoom](https://d3js.org/d3-zoom), and [D3 arcs](https://d3js.org/d3-shape/arc).

Remaining modules will be created separately after each preceding PR is tested and merged: cellular spatial structure, molecular structure, environmental input/response sliders, population Müller plot, and multiscale genomic tracks.
