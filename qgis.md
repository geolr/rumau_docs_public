# QGIS tips

## Calculate fields for x, y
Field Calculator expression: x ( @geometry )




# Other GIS
CRS

Ellipsoid = the mathematical Shape (defined by two numbers), (potato-shape)

Datum = the reference, contains ellipsoid definition

Projection = making a flat-2D representation of a 3D-shape, sheet of rubber, circle at the equiator gets distorted and bigger in area

Conservation in projections: Area, local angles = conformal, distances one-two points

Mercator projection: 16th century for sailing across the atlantic and give one direction (angle)

UTM projection: Universal Transfersal Mercator, not a reference system itself, can be applied to WGS84 and others, the full definition needs to specify which, good for North-South extents

Lambert Conformal Conic projection: good for East-West

EPSG has codes for both the geographic and the projected CRS'es

## WGS84
