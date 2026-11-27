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

## 04 — Environmental input and response

Open `04-environment-explorer.html` in Cursor using the same HTML preview workflow. Pinned React 18.3.1 and Plotly.js 2.35.2 load from CDNs; internet and JavaScript are required. No localhost, build, or WebGL is needed.

Continuously adjust oxygen availability, nutrients, drug exposure, and pH. The dashboard updates four clone-share cards, current/reference time curves, grouped comparison bars, a population-composition area chart, and a trait-change heatmap. Use the observation-day slider or Play/Pause to inspect the demonstration timeline. Click clone cards, curves, bars, or heatmap rows to emphasise a clone; Show all clones clears this emphasis. Plotly controls provide hover, zoom, pan, and chart PNG export.

Set current inputs as reference captures an independent comparison input set; subsequent edits compare against it at the same day. Differences are percentage points (population shares) or arbitrary score points (traits). Pinning the current inputs makes all differences zero. Reset dashboard restores inputs, reference, observation day, selection, and reference-curve visibility. Download response CSV includes all 61 demonstration days and both input settings in metadata comments.

The response calculation uses arbitrary coefficients and normalised exponential weights strictly to test the UI. It is not fitted, calibrated, or biologically validated; time and environmental labels do not imply measurements or treatment predictions. The composition chart is an ordinary stacked area plot and does not represent ancestry. Reference curves use the same invented response function with the saved reference inputs.

References: [Plotly updates](https://plotly.com/javascript/plotlyjs-function-reference/), [stacked area charts](https://plotly.com/javascript/filled-area-plots/), and [React integration](https://plotly.com/javascript/react/).

## 05 — Population ancestry / Müller plot

Open `05-muller-explorer.html` in Cursor with the same HTML preview workflow. Pinned D3.js 7.9.0 loads from a CDN; internet and JavaScript are required. No localhost or build is needed.

Ten invented clones form a founder and three branching families over 101 time samples. The layout recursively places each descendant envelope inside its parent; each parent's exclusive population is split around its children. A parent's enclosing polygon includes descendants, while its remaining visible colour represents only its own population. Inclusive lineage values must not be added across generations. Linear interpolation preserves nesting without spline overshoot. Runtime checks validate nonnegative populations, parent containment, sibling non-overlap, and inclusive/exclusive conservation at every sample.

Try relative/absolute scaling, clone selection from bands/legend/table/ancestry tree, observation-time slider and playback, emergence markers, band labels, overview brushing, Zoom to emergence, Reset explorer, and SVG/CSV exports. The inspector and table distinguish exclusive clone abundance from inclusive lineage abundance. Absolute mode shows arbitrary demo population units, not measured cell counts. The SVG exports the current plot window and selected emphasis. CSV contains all 101 times, parent IDs, emergence times, exclusive and inclusive values, and shares.

Every parent link, emergence event, and abundance trajectory is deterministic invented data, not reconstructed evolution. References: [ggmuller methodology](https://cran.r-project.org/web/packages/ggmuller/vignettes/ggmuller.html), [D3 areas](https://d3js.org/d3-shape/area), and [D3 brushing](https://d3js.org/d3-brush).

## 06 — Multiscale genomic atlas

Open `06-genomic-explorer.html` in Cursor with the same HTML preview workflow. Pinned Gosling.js 0.11.0, HiGlass 1.13.4, PixiJS 6.5.10 and React 18.3.1 load through browser import maps/CDNs. Internet access, JavaScript modules and WebGL are required. No localhost, npm installation or build step is needed.

The independent atlas contains a four-chromosome synthetic assembly (3.4 Mb), 16 invented genes with 64 exons, 24 clone-associated variants, 480 coarse signal bins and eight within-chromosome relationship arcs. A custom SVG circular overview also shows one invented cross-chromosome connection. Gosling renders linked linear gene/exon, variant, coverage, heatmap and relationship tracks. The overview's signal ring and location indicator update with navigation; the sequence lens displays 60 generated bases centred on the current single-chromosome viewport. Whole-genome mode uses a labelled example locus for the sequence lens until you choose a chromosome.

Try clicking a chromosome, Whole genome, searching `DEMO5` or `chr2:100000-200000`, pan/zoom buttons, wheel zoom and drag panning, gene shortcuts, track-layer switches, Reset atlas, and clicking a variant catalogue row. Hover or click plotted genes and variant points to inspect them. Select a variant row, then **Zoom tracks to these bases** to inspect the single-base locus and its underlined variant in the sequence lens. Clicking a base opens its nucleotide or variant annotation. The sequence lens is generated HTML linked to Gosling's viewport, not an externally fetched reference-sequence track. Signal bins remain coarse when zoomed in; zooming does not create additional signal resolution.

UI coordinates and variant positions are 1-based inclusive. Gene, exon and signal intervals use 0-based half-open boundaries internally and in JSON exports; the UI inspector converts gene starts to 1-based coordinates. Event order and sampling day are separate variant metadata, never the genomic x-axis. Sorting the catalogue by event order does not rearrange the genome. Coverage and signal scores are arbitrary demo units, not measured sequencing depth or expression. All bases, alleles, genes, links, clone associations and time annotations are invented and unvalidated.

Download tracks PNG exports the current Gosling canvas (not surrounding HTML controls, overview or sequence panel). Download locus JSON includes viewport coordinates, coordinate conventions, visible gene/variant records and the 60-base sequence lens. The original prototypes, combined application and previous enhanced HTML files remain unchanged.

References: [Gosling embedding](https://gosling-lang.org/docs/usage/), [composition](https://gosling-lang.org/docs/composition/), [inline data](https://gosling-lang.org/docs/data/) and [JavaScript API](https://gosling-lang.org/docs/js-api/). The browser module is pinned to the documented 0.11.0 embedding release; the current documentation may include newer features.

All six enhanced experiments now have separate standalone code files. They are not integrated into the original combined application.
