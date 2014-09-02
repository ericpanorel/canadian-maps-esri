## Overview

Canadian Base Maps using ESRI Javascript API (https://developers.arcgis.com/javascript/jsapi/), with information from here : http://geogratis.gc.ca/geogratis/DevCorner

Built using (barely) Google Web Starter Kit tooling (https://developers.google.com/web/starter-kit/) , meaning the codes are inside the app folder

### <a href='http://ericpanorel.github.io/canadian-maps-esri/index.html' target='_blank'>index.html</a>


Basemap = Geometry Only, Cached, Web Mercator: http://geoappext.nrcan.gc.ca/arcgis/rest/services/BaseMaps/CBMT_CBCT_GEOM_3857/MapServer

Text Overlay = English Text Only, Cached, Web Mercator: http://geoappext.nrcan.gc.ca/arcgis/rest/services/BaseMaps/CBMT_TXT_3857/MapServer

Hill Shader = Hillshade, Cached, LCC: http://geoappext.nrcan.gc.ca/arcgis/rest/services/BaseMaps/CBME_CBCE_HS_RO_3978/MapServer

Since the hill shader (EPSG:3978) is a different projection compared to the basemap (web mercator) so some trickery has to be performed by
implementing a sublass of esri.layers.DynamicMapServiceLayer

### <a href='http://ericpanorel.github.io/canadian-maps-esri/lcc.html' target='_blank'>lcc.html</a>
Lambert Conformal Conic projection (EPSG:3978) 

Basemap = English Combined, Cached, LCC: http://geoappext.nrcan.gc.ca/arcgis/rest/services/BaseMaps/CBMT3978/MapServer

Hill Shader = Hillshade, Cached, LCC: http://geoappext.nrcan.gc.ca/arcgis/rest/services/BaseMaps/CBME_CBCE_HS_RO_3978/MapServer

Much simpler, but the locate button didn't work perfectly until adding using <i>GeometryService</i>

### <a href='http://ericpanorel.github.io/canadian-maps-esri/wms.html' target='_blank'>wms.html</a>
Lambert Conformal Conic projection (EPSG:3978) 

Basemap = WMS: http://wms.ess-ws.nrcan.gc.ca/wms/toporama_en or http://wms.ess-ws.nrcan.gc.ca/wms/toporama_fr

Hill Shader = Hillshade, Cached, LCC: http://geoappext.nrcan.gc.ca/arcgis/rest/services/BaseMaps/CBME_CBCE_HS_RO_3978/MapServer

Using WMS as a base layer

Much simpler, but the locate button didn't work perfectly until adding using <i>GeometryService</i>


## License

Apache 2.0  
