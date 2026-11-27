# Visual tests

Six small, standalone browser prototypes for choosing BioScale visualizations. Each HTML file opens directly in Cursor's browser/preview and does not require a local development server.

## PR 1 — clone lineage tree

Open `clone-tree-d3.html` to try a clickable D3.js lineage tree with placeholder clone data.

## PR 2 — clone population evolution

Open `clone-population-d3.html` to compare simulated clone population shares across generations. Click a line or clone button to focus it.

## PR 3 — mutation order

Open `mutation-order-d3.html` to inspect a simulated clone's mutations in inferred evolutionary order. Click a marker for its biological interpretation.

## PR 4 — environmental effects

Open `environment-effects-d3.html` to adjust placeholder oxygen, drug exposure, and acidity values and compare clone fitness.

## PR 5 — spatial cell view (Three.js)

Open `cell-spatial-three.html` in Cursor to inspect the code, then run it using the same HTML preview workflow as the earlier files. No localhost server or npm installation is required. Internet access is required for the pinned Three.js 0.160.1 modules, and the preview must allow JavaScript and WebGL.

Drag to rotate, scroll to zoom, and click the nucleus, orange mitochondria, or blue/teal vesicles. The Inspect menu provides another way to select each object. Try Show membrane, Auto-rotate, and Reset view. All shapes, locations, measurements, and marker data are invented placeholders, not a validated biological model.

Built using the [Three.js documentation](https://threejs.org/docs/).

## PR 6 — molecular structure (3Dmol.js)

Open `protein-molecule-3dmol.html` in Cursor and run it using the same HTML preview workflow as the earlier files. No localhost server or npm installation is required. Internet access loads pinned 3Dmol.js 2.5.5; the preview must allow JavaScript and WebGL.

Drag to rotate, scroll to zoom, click atoms or select a residue, and switch between ball-and-stick, stick, and space-filling styles. Try Inspect demo mutation, Auto-rotate, and Reset view. The 96-atom, 24-residue backbone is generated placeholder geometry with explicit bonds, no side chains, and no hydrogens. R12H is an illustrative annotation, not a structural prediction or a real variant interpretation.

Built using the [3Dmol.js viewer documentation](https://3dmol.csb.pitt.edu/doc/glviewer/index.html).
