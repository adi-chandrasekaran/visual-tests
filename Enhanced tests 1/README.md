# Enhanced tests 1

New, independent visualization experiments. Original prototypes and the combined application are not modified by these enhancements. Each module is delivered as its own PR for manual testing and merging before the next module starts.

## 01 — Radial phylogenetic lineage

Open `01-radial-lineage.html` in Cursor and run using your HTML preview workflow. No localhost server or build is needed. Internet access loads pinned D3.js 7.9.0.

The atlas displays 128 synthetic observed clones, four coloured lineage groups, internal ancestors, and three annotation rings (clone state, mutation burden, and sampling day). Labels, branch colours, and ring colours have distinct meanings. Branch radii show cumulative invented divergence values; dotted extensions align terminal annotations. Topology mode instead aligns the tips and does not encode branch lengths.

Try selecting a node, branch, label, or ring; inspecting an ancestral group; filtering by lineage; searching for `CL-A001` and pressing Enter; hiding labels/rings; rotating, zooming, panning, and resetting; and downloading an SVG. Selection highlights a subtree and its ancestry. Tab through nodes and use Enter or Space to inspect them. The SVG export retains annotations and includes the current rotation and filtering, with pan/zoom reset to fit the figure.

All topology, divergence, variants, dates, and state labels are deterministic invented demo data, not inferred or validated biology. No time or genetic-distance calibration is claimed.

References: [D3 cluster layout](https://d3js.org/d3-hierarchy/cluster), [D3 zoom](https://d3js.org/d3-zoom), and [D3 arcs](https://d3js.org/d3-shape/arc).

## 02 — Cellular spatial explorer

Open `02-cellular-explorer.html` in Cursor and run with the same HTML preview workflow. It uses pinned React 18.3.1, React Three Fiber 8.17.10, and Three.js 0.170.0 directly from CDNs. No localhost, npm installation, or build step is needed; the preview needs internet access, JavaScript modules/import maps, and WebGL.

The procedural cell includes an irregular transparent membrane, nucleus with pore rings and nucleolus, 24 winding ER paths, 12 mitochondria with cristae, 7 stacked Golgi cisternae, 36 cytoskeletal filaments, and 30 vesicles. The scientific-style scene includes soft lighting/shadows, a coordinate grid, labels, selectable structures, and an inspector.

Try orbit/zoom/pan, selecting from the scene or Inspect menu, Focus structure, Isolate, layer visibility, membrane opacity, auto-rotation, the cross-section checkbox/axis/position slider, exploded view, scene PNG download, Overview, and Reset explorer. Clipping removes geometry on one side of the selected plane, including picking on that removed side; cut surfaces are uncapped. Exploded view intentionally offsets layers and is not a biological configuration. PNG export captures the 3D scene without HTML labels or controls.

All geometry is deterministic and invented, not measured or calibrated. Coordinates use arbitrary units. Reference: [React Three Fiber Canvas](https://r3f.docs.pmnd.rs/api/canvas) and [scene events](https://r3f.docs.pmnd.rs/api/events).

## 03 — Molecular structure explorer

Open `03-molecular-explorer.html` in Cursor and run with the same HTML preview workflow. Pinned Mol* 5.4.2 JavaScript/CSS loads from a CDN; internet access, JavaScript, and WebGL are required. No localhost, build, or external structure dataset is needed.

One synthetic folded protein and a synthetic ligand are generated as PDB text inside the file. Helix/sheet records explicitly describe the invented secondary structure. Side chains contain at most a Cβ marker: this is not a chemically validated or experimentally measured structure. The same coordinates support ribbon/cartoon, molecular surface, ball-and-stick, space-filling, and combined ribbon/surface views. Colour by secondary structure, sequence position, or uniform teal; adjust surface opacity, ligand visibility, and auto-rotation.

Click a sequence residue or the 3D protein to link the inspector and selection. Use a residue number, Focus, or Inspect demo variant to navigate. The variant at residue 12 is annotation only, not a mutation structure or effect prediction. Mol* controls expose native representation/component and screenshot tools. Download synthetic PDB exports the generated model. Reset view restores the default representation and camera.

References: [Mol* viewer guide](https://molstar.org/viewer-docs/), [plugin setup](https://molstar.org/docs/v5/plugin/instance/), and [selection model](https://molstar.org/docs/v5/plugin/selections/).

Remaining modules will be created separately after each preceding PR is tested and merged: environmental input/response sliders, population Müller plot, and multiscale genomic tracks.
