Drawing2Model User Manual
Drawing2Model User Manual
Created by George Joseph · Version of November 2026
1. What Drawing2Model does
Drawing2Model turns a 2D engineering drawing (PDF, DXF or DWG) into a 3D solid you
can inspect, colour, measure and export. It runs entirely in your browser: your drawings
are not uploaded anywhere.
Three conversion methods are available:
Extrude – a closed outline is pushed straight up to a thickness (plates, brackets,
gaskets).
Revolve – a half-profile is spun around a centre line (shafts, bushings, wheels, pins).
3 views – front, top and side silhouettes are intersected to rebuild a prismatic part.
Dashed lines can optionally be read to find blind holes and pockets.
The result can be exported as STL, OBJ, GLB or STEP.
2. Which edition to use
drawing_to_3d.html (online edition) – small file, loads its libraries from the internet
on first use. Use it when you are online.
drawing_to_3d_offline.html (offline edition) – one 15 MB file with every library inside.
It works with no internet, for example on a shop-floor laptop. Fonts fall back to your
system fonts.
Both editions behave identically. Open either file by double-clicking it; a current Chrome,
Edge, Firefox or Safari is recommended. No installation is needed.
3. The screen
Left sidebar – six numbered steps, from opening a file to choosing how the model
looks.
Centre pane (2D drawing) – your drawing. Drag to pan, scroll the wheel to zoom,
double-click to fit the drawing to the window.
Right pane (3D model) – the result. Drag to orbit, scroll to zoom, right-drag to pan.
Page 1 of 8Drawing2Model User Manual
Status bar (bottom left) – the current message. Green means success, red means a
problem you can fix.
4. Quick start (five minutes)
1. Under 1 · Open drawing, choose your PDF, DXF or DWG file.
2. Check 2 · Units & scale so the size shown matches reality (see section 6).
3. Pick a tab under 4 · Conversion – Extrude, Revolve or 3 views.
4. Follow the tab-specific steps in sections 8 to 10.
5. The 3D model updates automatically. Choose a colour under 6 · Render look.
6. Click an export button under 5 · 3D model.
5. Opening a drawing
DXF – read directly: lines, arcs, circles, ellipses, polylines, splines and blocks.
PDF – must be a vector PDF exported from CAD. Scanned or photographed drawings
contain no lines and cannot be read. If the PDF has several pages, the first page is
loaded.
DWG – read in the browser with the LibreDWG engine (about 8 MB, downloaded on
first use in the online edition). If a particular DWG fails, save it as DXF from your CAD
program (or convert it with the free ODA File Converter) and open the DXF instead.
After loading, the info line under the file button shows the number of curves, layers and
the overall size in millimetres.
6. Units and scale (step 2)
Getting the size right is the most important check.
1 drawing unit = ___ mm – how many millimetres one unit of the drawing is. DXF files
often have no unit stored, so check this. PDFs are set automatically (1 point = 0.3528
mm).
Drawing scale 1 : ___ – if the drawing is printed at, say, 1:2, enter 2 so the model comes
out at full size.
Calibrate from 2 points – the safest method. Click the button, click two points whose
real distance you know (clicks snap to line ends), then enter that distance in
millimetres. Units and scale are set for you.
Page 2 of 8Drawing2Model User Manual
After any change, look at the Size X×Y×Z line under the 3D model and compare it with a
dimension you trust.
7. Layers and line styles (step 3)
Every layer (DXF/DWG) or line style (PDF) is listed with the number of curves in it. Untick
a layer to hide its lines from the conversion.
All / None switch every layer at once.
Ignore dashed lines (center / hidden) – on by default, because dashed lines are
usually centre lines and hidden edges, not outlines. The two features that need
dashed lines (Revolve centre-line detection and 3-view hidden-line reading) work
even while this is ticked.
Hide layers that contain dimensions, hatching, text or the title block so only the part
outline remains.
8. Extrude
Use Extrude for a flat part with a constant thickness.
1. Select the Extrude tab.
2. Enter the Thickness in millimetres.
3. If the sheet has a border, title block or several parts, click Select region and drag a
rectangle around the one part you want. Whole drawing clears the region.
4. Shaded areas in the 2D view are what will be solid. Click an area to switch it between
solid and empty.
The settings shared by all tabs (Closed areas, Keep main outline only, Join tolerance) are
explained in section 11.
9. Revolve
Use Revolve for turned parts. Draw or provide a half-profile (one side of the part, from the
axis outwards) or a full section; the part is spun around the axis. Only the side of the axis
with positive radius is used.
1. Select the Revolve tab.
2. Click Select region and drag around the profile if the sheet contains other things.
Page 3 of 8Drawing2Model User Manual
3. Set the axis in one of three ways:
Detect centre line – finds the longest dashed or centre-layer line that is vertical
or horizontal inside the region. It also sets the direction automatically.
Pick on drawing – click on the drawing; the position snaps to nearby line ends.
Typing – choose Vertical line or Horizontal line and type the position in drawing
units.
Region edge – clears the typed position, so the left edge (vertical) or bottom
edge (horizontal) of the profile is used. This is right for a half-profile drawn
against its centre line.
4. The axis is drawn as a magenta dash-dot line labelled AXIS.
5. Sweep sets the angle: 360° for a full part, less for a cut-away view.
6. The quality list (Draft, Normal, Fine, Ultra) sets how many segments make up the
circle: 48, 96, 192 or 360. Normal is fine for most work; use Fine or Ultra for large,
smooth parts or before exporting.
Orientation: a vertical axis gives a part standing along Z. A horizontal axis gives a part
lying along X.
10. 3 views
Use 3 views when you have front, top and/or side views of a prismatic part and no single
outline. At least two views are needed.
1. Select the 3 views tab.
2. Choose the Projection: First angle (ISO-E, Europe and Asia) or Third angle (ISO-A,
USA). This decides which side the top and side views sit relative to the front view.
3. Click Auto-detect views. The tool finds up to three separate groups of lines and
labels them FRONT, TOP and SIDE with coloured dashed frames.
4. If a label is wrong or a view is missing, click Clear and draw the frames yourself with
the Front, Top and Side buttons (drag a rectangle around each view).
5. If the part looks mirrored, tick Mirror side view or Mirror top view.
The tool extrudes each view through the part and keeps only the space common to all of
them. Two views are enough for simple prismatic parts; the third refines the shape.
Page 4 of 8Drawing2Model User Manual
Reading dashed lines (experimental)
Silhouettes cannot show blind holes or pockets. Tick Read dashed lines: blind holes and
pockets to let the tool look for them:
An inner outline in one view (for example a circle in the top view) is treated as a hole
candidate.
The tool looks in another view for dashed lines running along the hole's walls. Their
length gives the hole depth.
A hole whose dashed walls reach the far surface becomes a through hole; otherwise it
is cut blind.
Detected holes are outlined in magenta in the 2D view, and a line under the option
reports how many were blind or through.
Inner outlines with no dashed evidence are ignored, not cut. Always check the result
against your drawing: dashed centre lines or other features in the same position can
mislead the depth.
11. Settings shared by all conversion tabs
Closed areas
Inner loops are holes – an outline inside another outline is a hole (default for
Extrude and Revolve).
Fill everything (silhouette) – inner outlines are filled (default for 3 views).
Keep main outline only – drops dimensions, arrows and notes that sit outside the
main part. Untick it if part of your drawing disappears.
Join tolerance – lines whose ends are closer than this (in drawing units) are treated
as connected. Increase it if an outline has tiny gaps and does not shade; decrease it if
separate parts merge.
Click a shaded area to switch it solid or empty. This is the quickest way to fix one
wrongly filled or missing area.
12. Chamfers and fillets (Extrude and Revolve)
Under the conversion tab, the Edges control rounds or bevels the part:
As drawn – no change.
Chamfer – a straight bevel of the size you enter.
Page 5 of 8Drawing2Model User Manual
Fillet – a rounded edge with the radius you enter.
Three options choose where it applies:
Profile corners – the sharp corners of the outline. In Extrude these are the vertical
edges; in Revolve they are the circular edges of a shaft.
Top and bottom edges – Extrude only: the edges around both faces.
Include inner corners – also treats inside corners and the edges of holes.
Rules of thumb:
Keep the size below half of the thinnest wall or step. If it is too large, the status bar
says so; enter a smaller value.
Very gentle curves in the outline are not mistaken for corners – only corners sharper
than about 20 degrees are treated.
Edges are not available in the 3 views tab.
13. The 3D model (step 5)
Build 3D rebuilds the model. With Auto update ticked, the model rebuilds a moment
after any change.
The text under the buttons shows the overall size in millimetres, the volume in cm³ and
the triangle count.
The line at the bottom of the step shows the geometry kernel state. The offline edition
adds the words offline edition.
Exporting
STL – a triangle mesh in millimetres, Z up. For 3D printing and most CAD viewers.
OBJ – a triangle mesh in millimetres, Z up.
GLB – a glTF file in metres, Y up (the glTF standard), with your render colour and
finish. For viewers, AR and web.
STEP – a solid made of planar faces, in millimetres, Z up, with your colour attached.
Flat and extruded faces export as true faces; curved surfaces (cylinders, fillets) are
faceted like an STL but remain a closed solid. Use it for measuring, as a reference body
in CAD, or for robot offline programming. It is not a feature-based CAD model, so you
cannot edit holes or fillets as parametric features.
Axes: X is width (the horizontal direction of the front view), Y is depth, Z is height.
Page 6 of 8Drawing2Model User Manual
14. Render look (step 6)
These settings change only how the model looks and are remembered in your browser
between sessions.
Colour swatches, custom colour and hex box – choose any colour. The 2D view's
shaded areas and the glow behind the model follow it.
Finish – Car paint (clear coat), Satin, Matte, Brushed metal, or Ghost (translucent).
Edge lines – dark outlines on sharp edges.
Wireframe overlay – shows the triangles.
Grid and floor shadow – the reference grid and the soft shadow on the floor.
Turntable rotation – slowly rotates the model.
Save render as PNG – saves the current 3D view with a transparent background.
15. Tips for good results
Clean the drawing first: hide dimension, hatch, text and title-block layers.
For Extrude and Revolve, make sure the outline is closed. A one-unit gap stops the
area from shading; raise the join tolerance to close small gaps.
Calibrate with two points whenever the unit is unknown.
For a part on a busy sheet, always use Select region.
For shafts, draw one half-profile and keep the dashed centre line in the drawing so
Detect centre line can find it.
Use 2 views for a simple block, 3 views for L-shapes and steps.
16. Troubleshooting
"No closed area selected" – nothing shaded. Check the layers, raise the join
tolerance, or click an area to make it solid.
Everything is shaded, including the border – use Select region, and keep Keep main
outline only ticked.
The model is the wrong size – recheck units, scale or calibrate with two points.
"Need at least 2 views" – auto-detect found fewer than two groups. Draw the frames
manually.
3D view is mirrored or the wrong way round – tick the mirror options, or check first
versus third angle.
Page 7 of 8Drawing2Model User Manual
"The profile is on the wrong side of the axis" – move the axis, or switch between
Vertical and Horizontal.
"Edge size is too large" or "Could not build the finished edges" – enter a smaller size.
"No dashed centre line found" – use Pick on drawing, or type the axis position.
"Geometry kernel failed to load" – the online edition could not reach the internet. Use
the offline edition.
A PDF shows no curves – it is probably a scan or contains text only.
A DWG fails to open – save it as DXF and load that.
17. Limits to be aware of
The tool reads vector geometry only; raster images are not supported.
3 views rebuilds the common volume of the views. It cannot recover features hidden
in every view unless the dashed-line option finds them.
The dashed-line option is experimental and should be checked against the drawing.
STEP output is faceted for curved surfaces and is not parametric.
Very large drawings with tens of thousands of curves may take a few seconds to
process.
18. Credits
Drawing2Model was created by George Joseph. It uses open-source libraries: three.js (3D
display), manifold-3d (solid geometry), pdf.js (PDF reading) and LibreDWG (DWG
reading).
Page 8 of 8
