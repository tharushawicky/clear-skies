# Clear Skies

An interactive atlas of Sentinel-2 scenes over Sri Lanka. Open `dist/index.html` through any static HTTP server. No API keys or build step required. Leaflet, web fonts and basemap tiles require internet access.

## Data and AWS

100 real STAC features fetched October 31, 2026 from:
https://earth-search.aws.element84.com/v1/search?collections=sentinel-2-l2a&bbox=79.5,5.8,82,9.9&datetime=2025-01-01T00:00:00Z/2025-02-01T00:00:00Z&limit=100

This is a bounded sample, not all scenes in the region or month. The snapshot preserves source metadata and geometries. Thumbnails and RGB COG links point directly to the public sentinel-cogs Amazon S3 bucket. S3 is the app's AWS data service; hosting and OpenStreetMap basemap are separate. No Amazon Location Service or AWS account provisioning is claimed.

Dataset: https://registry.opendata.aws/sentinel-2-l2a-cogs/
Contains modified Copernicus Sentinel data (2025), processed by Element 84. Follow the dataset's terms. Basemap © OpenStreetMap contributors. Leaflet BSD-2-Clause.

## Explore

Filter cloud percentage, sort by clearest or newest, click a footprint or scene card, open the original S3 RGB GeoTIFF, and export the filtered features as GeoJSON. Cloud percentages apply to entire scenes, not point weather. Resolution is the underlying RGB band's 10 m pixel size; thumbnails are downsampled.

## Checks

`node --check dist/app.js`. Dataset checked for 100 features; representative S3 thumbnail and RGB asset returned HTTP 200. Test the map in a browser before recording a demo. External CDN/tile availability affects rendering.
