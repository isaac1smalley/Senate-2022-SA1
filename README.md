<!doctype html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="initial-scale=1,user-scalable=no,maximum-scale=1,width=device-width">
        <meta name="mobile-web-app-capable" content="yes">
        <meta name="apple-mobile-web-app-capable" content="yes">
        <link rel="stylesheet" href="css/leaflet.css">
        <link rel="stylesheet" href="css/qgis2web.css"><link rel="stylesheet" href="css/fontawesome-all.min.css">
        <style>
        html, body, #map {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
        }
        </style>
        <title></title>
    </head>
    <body>
        <div id="map">
        </div>
        <script src="js/qgis2web_expressions.js"></script>
        <script src="js/leaflet.js"></script>
        <script src="js/leaflet.rotatedMarker.js"></script>
        <script src="js/leaflet.pattern.js"></script>
        <script src="js/leaflet-hash.js"></script>
        <script src="js/Autolinker.min.js"></script>
        <script src="js/rbush.min.js"></script>
        <script src="js/labelgun.min.js"></script>
        <script src="js/labels.js"></script>
        <script src="data/SA1_Fed22_merged_0.js"></script>
        <script src="data/Newdistrictsandregions_1.js"></script>
        <script>
        var map = L.map('map', {
            zoomControl:true, maxZoom:28, minZoom:1
        }).fitBounds([[-38.051799530983295,144.5749840018447],[-37.77645327448313,145.01279664395184]]);
        var hash = new L.Hash(map);
        map.attributionControl.setPrefix('<a href="https://github.com/tomchadwin/qgis2web" target="_blank">qgis2web</a> &middot; <a href="https://leafletjs.com" title="A JS library for interactive maps">Leaflet</a> &middot; <a href="https://qgis.org">QGIS</a>');
        var autolinker = new Autolinker({truncate: {length: 30, location: 'smart'}});
        var bounds_group = new L.featureGroup([]);
        function setBounds() {
        }
        function pop_SA1_Fed22_merged_0(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA1_CODE21'] !== null ? autolinker.link(feature.properties['SA1_CODE21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['CHG_FLAG21'] !== null ? autolinker.link(feature.properties['CHG_FLAG21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['CHG_LBL21'] !== null ? autolinker.link(feature.properties['CHG_LBL21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA2_CODE21'] !== null ? autolinker.link(feature.properties['SA2_CODE21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA2_NAME21'] !== null ? autolinker.link(feature.properties['SA2_NAME21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA3_CODE21'] !== null ? autolinker.link(feature.properties['SA3_CODE21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA3_NAME21'] !== null ? autolinker.link(feature.properties['SA3_NAME21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA4_CODE21'] !== null ? autolinker.link(feature.properties['SA4_CODE21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA4_NAME21'] !== null ? autolinker.link(feature.properties['SA4_NAME21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['GCC_CODE21'] !== null ? autolinker.link(feature.properties['GCC_CODE21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['GCC_NAME21'] !== null ? autolinker.link(feature.properties['GCC_NAME21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['STE_CODE21'] !== null ? autolinker.link(feature.properties['STE_CODE21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['STE_NAME21'] !== null ? autolinker.link(feature.properties['STE_NAME21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['AUS_CODE21'] !== null ? autolinker.link(feature.properties['AUS_CODE21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['AUS_NAME21'] !== null ? autolinker.link(feature.properties['AUS_NAME21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['AREASQKM21'] !== null ? autolinker.link(feature.properties['AREASQKM21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['LOCI_URI21'] !== null ? autolinker.link(feature.properties['LOCI_URI21'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA1_Fed22_'] !== null ? autolinker.link(feature.properties['SA1_Fed22_'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SA1_Fed2_1'] !== null ? autolinker.link(feature.properties['SA1_Fed2_1'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['grn_by_pp_'] !== null ? autolinker.link(feature.properties['grn_by_pp_'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['grn_by_p_1'] !== null ? autolinker.link(feature.properties['grn_by_p_1'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['grn_by_p_2'] !== null ? autolinker.link(feature.properties['grn_by_p_2'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['grn_by_p_3'] !== null ? autolinker.link(feature.properties['grn_by_p_3'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['grn_by_p_4'] !== null ? autolinker.link(feature.properties['grn_by_p_4'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['grn_by_p_5'] !== null ? autolinker.link(feature.properties['grn_by_p_5'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['grn_by_p_6'] !== null ? autolinker.link(feature.properties['grn_by_p_6'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_SA1_Fed22_merged_0_0(feature) {
            if (feature.properties['grn_by_p_3'] >= 0.600000 && feature.properties['grn_by_p_3'] <= 11.238000 ) {
                return {
                pane: 'pane_SA1_Fed22_merged_0',
                opacity: 1,
                color: 'rgba(35,35,35,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(247,252,245,1.0)',
                interactive: true,
            }
            }
            if (feature.properties['grn_by_p_3'] >= 11.238000 && feature.properties['grn_by_p_3'] <= 21.876000 ) {
                return {
                pane: 'pane_SA1_Fed22_merged_0',
                opacity: 1,
                color: 'rgba(35,35,35,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(201,234,194,1.0)',
                interactive: true,
            }
            }
            if (feature.properties['grn_by_p_3'] >= 21.876000 && feature.properties['grn_by_p_3'] <= 32.514000 ) {
                return {
                pane: 'pane_SA1_Fed22_merged_0',
                opacity: 1,
                color: 'rgba(35,35,35,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(123,199,124,1.0)',
                interactive: true,
            }
            }
            if (feature.properties['grn_by_p_3'] >= 32.514000 && feature.properties['grn_by_p_3'] <= 43.152000 ) {
                return {
                pane: 'pane_SA1_Fed22_merged_0',
                opacity: 1,
                color: 'rgba(35,35,35,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(42,146,75,1.0)',
                interactive: true,
            }
            }
            if (feature.properties['grn_by_p_3'] >= 43.152000 && feature.properties['grn_by_p_3'] <= 53.790000 ) {
                return {
                pane: 'pane_SA1_Fed22_merged_0',
                opacity: 1,
                color: 'rgba(35,35,35,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(0,68,27,1.0)',
                interactive: true,
            }
            }
        }
        map.createPane('pane_SA1_Fed22_merged_0');
        map.getPane('pane_SA1_Fed22_merged_0').style.zIndex = 400;
        map.getPane('pane_SA1_Fed22_merged_0').style['mix-blend-mode'] = 'normal';
        var layer_SA1_Fed22_merged_0 = new L.geoJson(json_SA1_Fed22_merged_0, {
            attribution: '',
            interactive: true,
            dataVar: 'json_SA1_Fed22_merged_0',
            layerName: 'layer_SA1_Fed22_merged_0',
            pane: 'pane_SA1_Fed22_merged_0',
            onEachFeature: pop_SA1_Fed22_merged_0,
            style: style_SA1_Fed22_merged_0_0,
        });
        bounds_group.addLayer(layer_SA1_Fed22_merged_0);
        map.addLayer(layer_SA1_Fed22_merged_0);
        function pop_Newdistrictsandregions_1(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? autolinker.link(feature.properties['id'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['DISTRICT'] !== null ? autolinker.link(feature.properties['DISTRICT'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['REGION'] !== null ? autolinker.link(feature.properties['REGION'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_Newdistrictsandregions_1_0() {
            return {
                pane: 'pane_Newdistrictsandregions_1',
                opacity: 1,
                color: 'rgba(53,121,177,1.0)',
                dashArray: '',
                lineCap: 'square',
                lineJoin: 'bevel',
                weight: 4.0,
                fillOpacity: 0,
                interactive: true,
            }
        }
        map.createPane('pane_Newdistrictsandregions_1');
        map.getPane('pane_Newdistrictsandregions_1').style.zIndex = 401;
        map.getPane('pane_Newdistrictsandregions_1').style['mix-blend-mode'] = 'normal';
        var layer_Newdistrictsandregions_1 = new L.geoJson(json_Newdistrictsandregions_1, {
            attribution: '',
            interactive: true,
            dataVar: 'json_Newdistrictsandregions_1',
            layerName: 'layer_Newdistrictsandregions_1',
            pane: 'pane_Newdistrictsandregions_1',
            onEachFeature: pop_Newdistrictsandregions_1,
            style: style_Newdistrictsandregions_1_0,
        });
        bounds_group.addLayer(layer_Newdistrictsandregions_1);
        map.addLayer(layer_Newdistrictsandregions_1);
        setBounds();
        </script>
    </body>
</html>
