# QGIS tips

## Calculate fields for x, y
Field Calculator expression: x ( @geometry )

Vector > Geometry Tools > Add Geometry Attributes (but this creates a new layer with additional attributes)

Copy paste from Attribute table (F6) would include a `Point (12345.123 98765.987)` as first column `wkt_geom` :-D thus no need sometimes


## Databases
`DB Manager` in menu `Database`

Query for filtering to only get a layer with a subset of data: 

```
SELECT * 
FROM "<tablename>"."api_well"
WHERE "api_well"."basin_identifier"Like( 'Rhine')
```


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

#### Links
CRS-Talk: https://video.osgeo.org/w/iAh2NTveFJ7ByQQaNm79Sc
