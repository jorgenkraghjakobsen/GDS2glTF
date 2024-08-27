# Python3 GDS to glTF files converter script

This first version was built to create `.glTF` 3D files from SDK130 PDK `.gds` files

Lot of the work is based on the gdsiistl repo: https://github.com/dteal/gdsiistl

This is a fork of GDS to glTF converter 

Layerstack is now read in from a file to support different technologys
The directory 'layerstack' has layerstack for IHP sg13g2 and Skywater sky130

Python libraries requirements:
```
numpy
gdspy
triangle
pygltflib
```

## Usage:
`python3 gds2gltf.py file.gds layerstack.txt` 

Outputs a `file.gds.gltf` in the same folder as the original gds file


## Note from original gdsiistl script:

Due to a limitation of the library used to triangulate the polygonal boundaries of the GDSII geometry, the polygon borders (i.e., all geometry) are shifted slightly (by a hardcoded delta of about 0.00001 units, or 0.01 nanometers in standard micron units) before export. Furthermore, due to another related limitation/bug (not yet completely understood; see source code comments), extra triangles are sometimes created covering holes in polygons.

So the output mesh is not guaranteed to be watertight, perfectly dimensioned, or retain all polygon holes, but it should be arbitrarily close and err on the side of extra triangles, so a program (e.g., Blender) can edit the mesh by deleting faces and produce a negligibly-far-from perfect visualization.









