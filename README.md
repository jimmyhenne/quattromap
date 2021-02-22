# Inhaltsverzeichnis

- [QuattroMap](#quattromap)
    - [Messwerkzeuge](#messwerkzeuge)
  - [Aktuell verf�gbare Dienste](#aktuell-verf-gbare-dienste)
    - [Layer](#layer)
    - [Overlays](#overlays)
  - [Permalink](#permalink)
  - [Konfiguration](#konfiguration)
  - [CodeSandbox](#codesandbox)
  - [Develop](#develop)
    - [Search](#search)

# QuattroMap

[![GitHub CI status](https://github.com/kreis-viersen/quattromap/workflows/ci/badge.svg)][github-action-ci]
[![License](https://img.shields.io/badge/license-MIT-blue.svg)][license]

[github-action-ci]: https://github.com/kreis-viersen/quattromap/actions?query=workflow%3Aci
[license]:          https://tldrlegal.com/license/mit-license

<a href="https://kreis-viersen.github.io/quattromap/"><img src="./quattromap_screenshot.png"></a>

QuattroMap ist eine vom Kreis Viersen entwickelte Kartenanwendung, die vor allem die Au�endienstt�tigkeiten unterst�tzen kann.

Das Tool ist unter https://kreis-viersen.github.io/quattromap/ von jedem internetf�higen Ger�t, wie Tablet, Smartphone, Laptop und PC, erreichbar. Die Anwendung ist kompatibel mit modernen Browsern, wie Mozilla Firefox, Google Chrome, Safari. Der Microsoft Internet Explorer wird nicht mehr unterst�tzt, da Mapbox-gl-js seine Unterst�tzung seit Verion 2.0.0 ablehnt!

Mit Hilfe der Anwendung k�nnen bis zu 4 verschiedene Karten mit gleichem Kartenausschnitt gleichzeitig dargestellt werden.
�ber die Schaltfl�che in der linken unteren Ecke gelangt man zu den Einstellungen der Kartenfenster. Zur Auswahl der Kartenhintergr�nde stehen z. B.
Luftbilder, Liegenschaftskataster, geplante Geb�ude oder OpenStreetMap zur Verf�gung.

In den Kartenfenstern k�nnen auch �berlagerungen (Overlays) benutzt werden, um bspw. Luftbilder und geplante Geb�ude �bereinander zu legen.

Am rechten Bildschirmrand gibt es eine Suchfunktion (Mapbox GL Geocoder Control: https://github.com/mapbox/mapbox-gl-geocoder) sowie die M�glichkeit den Kartenausschnitt und den eigenen Standort �ber die Standortbestimmung des Ger�ts anzuzeigen (Standortbestimmung muss im Ger�t eingeschaltet bzw. erlaubt sein).
Dazu gibt es dort eine Schaltfl�che, um die Anwendung im Vollbild anzuzeigen. Ein Klick auf das Kompass-Symbol richtet die Karte(n) wieder nach Norden aus.

### Messwerkzeuge

Sobald nur eine Karte angezeigt wird, stehen Messwerkzeuge zur Verf�gung:
- LineString: zum Messen einer Entfernung in Metern
- Polygon: zum Messen einer Fl�che in Quadratmetern

Einfach das gew�nschte Werkzeug ausw�hlen, den LineString oder das Polygon auf der Karte zeichen und mit einem Klick auf den letzten St�tzpunkt abschlie�en:

<img src="./quattromap_measurement-tools.gif" width="715">

## Aktuell verf�gbare Dienste

### Layer

|Name|Art|URL|Dienste Layer|
|:---|:---|:---|:---|
|**Geobasis NRW**||||
|NRW Luftbild Farbe|WMS|https://www.wms.nrw.de/geobasis/wms_nw_dop?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|nw_dop_rgb|  
|NRW vDOP Farbe|WMS|https://www.wms.nrw.de/geobasis/wms_nw_vdop?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|nw_vdop_rgb|  
|NRW ALKIS FLURST�CKE|WMS|https://www.wms.nrw.de/geobasis/wms_nw_alkis?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|adv_alkis_flurstuecke|  
|NRW Amtliche Basiskarte (ABK)|WMS|https://www.wms.nrw.de/geobasis/wms_nw_abk?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|WMS_NW_ABK|  
|NRW Alkis TN|WMS|https://www.wms.nrw.de/geobasis/wms_nw_alkis?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|adv_alkis_tatsaechliche_nutzung|
|NRW Schummerung|WMS|https://www.wms.nrw.de/geobasis/wms_nw_dgm-schummerung?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|nw_dgm-schummerung_pan|
|NRW DTK|WMS|https://www.wms.nrw.de/geobasis/wms_nw_dtk?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|nw_dtk_col|
|NRW TDOM|WMS|https://www.wms.nrw.de/geobasis/wms_nw_tdom?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|nw_tdom|
|**OpenStreetMap**||||
|OSM Mapnik|XYZ Tiles|https://www.openstreetmap.org||
|**RVR**||||
|RVR Luftbild Farbe|WMS|https://geodaten.metropoleruhr.de/dop/dop?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|dop|
|**KRZN-Dienste**||||
|Kreis Viersen ALKIS|WMS|https://gdi-niederrhein-geodienste.de/flurkarte_verb_sammeldienst/service?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|FlurkarteAdV_Viersen|
|Stadt Krefeld ALKIS|WMS|https://gdi-niederrhein-geodienste.de/flurkarte_verb_sammeldienst/service?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|FlurkarteAdV_Krefeld|
|Kreis Wesel ALKIS|WMS|https://gdi-niederrhein-geodienste.de/flurkarte_verb_sammeldienst/service?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|FlurkarteAdV_Wesel|
|Kreis Kleve ALKIS|WMS|https://gdi-niederrhein-geodienste.de/flurkarte_verb_sammeldienst/service?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|FlurkarteAdV_Kleve|
|Stadt Bottrop ALKIS|WMS|https://gdi-niederrhein-geodienste.de/flurkarte_verb_sammeldienst/service?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|Flurkarte_Bottrop|
|Kreis Viersen ALKIS light|WMS|https://geoservices.krzn.de/security-proxy/services/wms_kvie_alkis_light?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|nutzungsarten, flurstuecke, gebaeude, lagebezeichnungen|
|Kreis Viersen Geplante Geb�ude|WMS|https://geoservices.krzn.de/security-proxy/services/wms_kvie_geplgeb?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|kvie_geplgeb|
|**Nationaal Georegister (NL)**||||
|NL Luftbild Farbe|WMS|https://geodata.nationaalgeoregister.nl/luchtfoto/rgb/wms?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|Actueel_ortho25|  
|**Kreis Warendorf**||||
|Kreis Warendorf ALKIS|WMS|https://www.kreis-warendorf.de/arcgis/service2?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|alkis_lieka|  
|Kreis Warendorf ABK 1:5000|WMS|https://www.kreis-warendorf.de/arcgis/service2?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|abk5000|  
|**Kreis Steinfurt**||||
|Kreis Steinfurt ALKIS|WMS|https://gis.kreis-steinfurt.de/arcgis13/services/Geobasisdaten/Geobasisdaten_Kreissuebersichtskarte_DTK_farbe/MapServer/WMSServer?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|0|
|Kreis Steinfurt ABK|WMS|https://gis.kreis-steinfurt.de/arcgis13/services/Geobasisdaten/Geobasisdaten_ABK_farbe/MapServer/WMSServer?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|0|

### Overlays

Zus�tzlich zu den unter [Layer](https://github.com/kreis-viersen/quattromap#layer) gelisteten Diensten sind als Overlay verf�gbar:

|Name|Art|URL|Dienste Layer|
|:---|:---|:---|:---|
|**Geobasis NRW**||||
|NRW TDOM Metadaten|WMS|https://www.wms.nrw.de/geobasis/wms_nw_tdom?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|nw_tdom_info|
|NRW Luftbild Overlay|WMS|https://www.wms.nrw.de/geobasis/wms_nw_dop_overlay?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|WMS_NW_DOP_OVERLAY|  
|NRW LINFOS|WMS|https://www.wms.nrw.de/umwelt/linfos?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities|Naturschutzgebiete, Landschaftsschutzgebiet|

## Permalink

Die URL enth�lt die derzeitige Einstellung der QuattroMap (Permalink). Dazu geh�rt die Anzahl und Einstellung der Kartenfenster inkl. Layerdefinitionen, das Kartenzentrum und die Zoomstufe. �ber den Permalink k�nnen so vordefinierte Anwendungen als Lesezeichen gespeichert oder weitergegeben werden. �ber die Schaltfl�che *Permalink in die Zwischenablage kopieren* am linken Bildschirmrand wird die derzeitige URL in die Zwischenablage kopiert und kann dann bspw. per Mail geteilt werden.

## Konfiguration

�ber die [config.json](./src/config.json) k�nnen einige Standardeinstellungen der QuattroMap vorgenommen werden.

|Parameter|Erkl�rung|Beispiel|
|:---|:---|:---|
|"center"|Gibt die Zentrumskoordinate des Kartenfensters beim Starten an. Angabe geographisch mit L�ngen- und Breitenangabe in EPSG 4326.|"center": [6.391263, 51.258812]|
|"zoom"|Definiert die Zoomstufe beim Start. Wertebereich: 0 (fern) - 22 (nah)|"zoom": 16|
|"maps"|Optionale Angabe �ber die Anzahl der Kartenfenster. M�gliche Werte: 1, 2, 3, 4; Standardwert: 4| "maps": 2|
|"crosshair"| Optionale Definition der Fadenkreuzfarbe. M�gliche Werte: black, red, orange, yellow, green, blue, pink; Standardwert: black|"crosshair": "red"|
|"map_x": {"layer": `layername`} *Optional*: "overlay": `layername`, "overlay_opacity": `opacity-value`, }|Voreinstellung der dargestellten Dienste des Kartenfensters x (1-4) beim Starten der QuattroMap. `layer` enth�lt einen Namen eines Dienstes, die unter "layer" definiert sind. `overlay` enth�lt einen Namen eines Dienstes, der als Abdeckungslayer dient und muss nur angegeben werden, wenn ein Abdeckungslayer verwendet werden soll. `overlay_opacity` definiert die Deckkraft des Abdeckungslayers. M�gliche Werte: 0 (transparent) - 1 (opak); Standardwert: 0.5| "map_1": {"layer": "NRW Luftbild Farbe", "overlay": "NRW Schummerung", "overlay_opacity": 0.4}|
|"layer": [ .. ]|Enth�lt die Definitionen der w�hlbaren Dienste im Dropdown Men�||
|"name"|Name des Dienstes, der im Dropdown Men� und beim Klick auf den Info-Button erscheint.|"name": "NRW Alkis TN"|
|"attribution"|Attribution zur Beschreibung der verwendeten Dienste, die �ber den Info-Button dargestellt wird. HTML-Tags k�nnen verwendet werden.|"attribution": "Land NRW (2021) Deutschland ? Zero ? Version 2.0 (`<a target='_blank' rel='noopener noreferrer' href='https://www.govdata.de/dl-de/zero-2-0'>www.govdata.de/dl-de/zero-2-0</a>`)"|
|"url"|URL des WMS 1.3.0 Dienstes oder OpenStreetMap XYZ-Tiles|"url": "`https://www.wms.nrw.de/geobasis/wms_nw_alkis`"|
|"layer"|Darzustellende Layer des Dienstes. Mehrere Layer werden mit Komma getrennt.|"layer": "nutzungsarten,flurstuecke"|
|"format"| Abzurufendes Rasterformat (`png` oder `jpeg`) der Kacheln. Da png Transparenz erm�glicht, ist png zu empfehlen. Jedoch k�nnen nicht alle Dienste png liefern.|"format": "png"|
|"category"|Begriff zur Kategorisierung der Dienste im Dropdown-Men�.|"category": "GeoBasis NRW"|
|"onlyOverlay"|Mit diesem optionalen Parameter l�sst sich der entsprechende Dienst nur als Overlay verwenden.|"onlyOverlay": true|
|"style"|Optionaler Parameter zur Auswahl eines bestimmten Stils. Stile k�nnen von Diensten angeboten werden.|"style": "Farbe"|

## CodeSandbox

In diesem Repository werden f�r jeden Pull Request �ber einen CodeSandbox-Bot automatisch �nderungen in einer isolierten Testumgebung kompiliert und k�nnen so im Vorfeld getestet werden. Hierzu ist in einem Pull Request im Beitrag von CodeSandbox auf den Link *quattromap* zu klicken. Im neu ge�ffneten Fenster kann das Tool durch einen Klick auf die parallel versetzten Rechtecke in der oberen rechten Ecke des Kartenfenster auf Vollbild maximiert werden.

<img src="./codesandbox_fullscreen.png">

## Develop

```bash
# clone the repository
git clone https://github.com/kreis-viersen/quattromap/
cd quattromap
```
Install the deps, start the dev server and open the web browser on `http://localhost:8080/`.

```bash
# install dependencies
npm install
# start dev server
npm start
```

The build process will watch for changes to the filesystem, rebuild and autoreload QuattroMap. However note this from the [webpack-dev-server docs](https://webpack.js.org/configuration/dev-server/):

> webpack uses the file system to get notified of file changes. In some cases this does not work. For example, when using Network File System (NFS). Vagrant also has a lot of problems with this. In these cases, use polling. ([snippet source](https://webpack.js.org/configuration/dev-server/#devserverwatchoptions-))

```bash
# build the app
npm run build
```
Once the build is finished, you'll find it at `dist/`.

```bash
# publish files to a gh-pages branch on GitHub
npm run deploy
```

### Search

For the search functionality https://github.com/mapbox/mapbox-gl-geocoder is used.

For your own QuattroMap please use your own access token:
https://docs.mapbox.com/help/how-mapbox-works/access-tokens/.
