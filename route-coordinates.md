# 🗺️ Route Coordinates & GIS Data

This file contains the raw GPS coordinates for the walking and biking routes, useful for importing into mapping tools (Google My Maps, QGIS, etc.).

## Route Waypoints

| Waypoint | Latitude | Longitude | Description |
|----------|----------|-----------|-------------|
| Origin | 40.0448805 | -105.2738879 | 45 Oak Avenue, Boulder |
| Waypoint 1 | 40.039879 | -105.272735 | Oak Ave / 19th St area |
| Waypoint 2 | 40.037878 | -105.272709 | 19th Street corridor |
| Waypoint 3 | 40.036816 | -105.272707 | Approaching 20th St |
| Waypoint 4 | 40.034653 | -105.272691 | 20th Street segment |
| Waypoint 5 | 40.030067 | -105.27266 | Near Pearl Street |
| Waypoint 6 | 40.025592 | -105.272523 | 18th Street area |
| Waypoint 7 | 40.019579 | -105.271751 | Canyon Blvd corridor |
| Waypoint 8 | 40.017295 | -105.272649 | Approaching Broadway |
| Destination | 40.0163281 | -105.2789726 | 1800 Broadway, Boulder |

## Full Route Geometry

The complete route linestring (simplified) follows this general path:
```
Start: 40.0448805, -105.2738879 (Oak Avenue)
  → 40.039879, -105.272735 (19th St)
  → 40.034653, -105.272691 (20th St corridor)
  → 40.030067, -105.27266 (Pearl St area)
  → 40.025592, -105.272523 (18th St area)
  → 40.019579, -105.271751 (Canyon Blvd)
End: 40.0163281, -105.2789726 (1800 Broadway)
```

## Use with Google My Maps

1. Go to [Google My Maps](https://mymaps.google.com)
2. Click "Create a New Map"
3. Click "Add Layer" → "Import"
4. Copy/paste the coordinates above
5. Style your route (green for walking, blue for biking)
6. Share with your community!

## Use with QGIS / GeoJSON

The route can be converted to a GeoJSON Feature:
```json
{
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [-105.2738879, 40.0448805],
      [-105.272735, 40.039879],
      [-105.272709, 40.037878],
      [-105.272707, 40.036816],
      [-105.272691, 40.034653],
      [-105.27266, 40.030067],
      [-105.272523, 40.025592],
      [-105.271751, 40.019579],
      [-105.2789726, 40.0163281]
    ]
  },
  "properties": {
    "name": "Boulder Green Commute Route",
    "mode": "walking/biking",
    "distance_km": 4.03
  }
}
```