
<!DOCTYPE html>
<html>
<head>
<title>Brython test</title>
<meta charset="iso-8859-1">
<meta name="viewport" content="user-scalable=no, width=device-width, initial-scale=1,maximum-scale=1">
<meta name="apple-mobile-web-app-capable" content="yes">
<script src="https://cdn.jsdelivr.net/npm/brython@3/brython.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/brython@3/brython_stdlib.js"></script>





<link rel="stylesheet" type="text/css" href="navi.css" />
<link rel="apple-touch-icon" href="icon.png"/>
<link rel="apple-touch-startup-image" href="splash.png">

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css"
   integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A=="
   crossorigin="anonymous"/>


 <!-- Make sure you put this AFTER Leaflet's CSS -->
 <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"
   integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA=="
   crossorigin="anonymous"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/proj4js/2.8.0/proj4.js"></script>
<!--<script src="https://unpkg.com/proj4leaflet@1.0.2/src/proj4leaflet.js"></script>-->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/proj4leaflet/1.0.2/proj4leaflet.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/proj4leaflet/1.0.2/proj4leaflet.min.js"></script>

<script src="easy-button.js"></script>
<script type="text/python" src="show_source.py"></script>
<style>

#container{
    text-align: center;
}
#mapid{
    height: 800px;
    width: 1000px;
}

.img-overlay-wrap {
  position: relative;
  display: inline-block; /* <= shrinks container to image size */
}
.img-overlay-wrap svg {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1000;
}


.img-overlay-wrap mapid {
  position: absolute;
  top: 0;
  left: 0;
}

.gizmo {
  fill: #94a3ab;
  transition: 0.5s;
}

.gizmo:hover {

  filter: brightness(150%) drop-shadow( 0px 0px 3px rgba(200, 255, 200, 1));
}

.svgbutton {
  fill: #94a3ab;
  transition: 0.5s;
}

.svgbutton:hover {

  filter: brightness(150%) drop-shadow( 0px 0px 3px rgba(200, 255, 200, 1));
}

.play2 {
  fill: #94a3ab;
  transition: 0.5s;
}

.play2:hover {
  filter: brightness(150%) drop-shadow( 0px 0px 3px rgba(200, 255, 200, 1));
}

.svgtxt{
  -webkit-touch-callout: none;
  -webkit-user-select:none;
  -khtml-user-select:none;
  -moz-user-select:none;
  -ms-user-select:none;
  -o-user-select:none;
  user-select:none;
}



.img-overlay-wrap test2 {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
}
}
</style>

</head>
<body onLoad="brython(1)">
<i class="fa-solid fa-star"></i>
<i class="fa-regulars fa-star"></i>
<!--<div id="header">-->
<!--    <H1>Your position</H1>-->
<!--</div>-->

<div id="header"><img src="header.svg"></div>
<div id="container">
<!--    <div id="coords"></div>-->
    <div class="img-overlay-wrap">
        <div id="mapid"></div>
<!--        <div id="test2">dsds</div>-->


<svg
   id="root"
   version="1.1"
   viewBox="0 0 610 439"
   height="800px"
   width="1000px"
   style="pointer-events:none"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:svg="http://www.w3.org/2000/svg"
   xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
   xmlns:cc="http://creativecommons.org/ns#"
   xmlns:dc="http://purl.org/dc/elements/1.1/">
  <metadata
     id="metadata3795">
    <rdf:RDF>
      <cc:Work
         rdf:about="">
        <dc:format>image/svg+xml</dc:format>
        <dc:type
           rdf:resource="http://purl.org/dc/dcmitype/StillImage" />
      </cc:Work>
    </rdf:RDF>
  </metadata>
  <defs
     id="defs33">
    <linearGradient
       gradientTransform="translate(-30.101538,21.96)"
       id="cmapGrad"
       gradientUnits="userSpaceOnUse"
       y2="367.66486"
       x2="590.35651"
       y1="367.66486"
       x1="490.68201">
      <stop
         id="stop5678"
         offset="0"
         style="stop-color:#f0001a;stop-opacity:0.91489273;" />
      <stop
         id="stop5691"
         offset="0.48991847"
         style="stop-color:#ffffff;stop-opacity:0.95294118;" />
      <stop
         id="stop5680"
         offset="1"
         style="stop-color:#3370d7;stop-opacity:1;" />
    </linearGradient>
    <filter
       height="1.640227"
       width="1.0414588"
       y="-0.32011349"
       x="-0.020729406"
       id="filter2251"
       style="color-interpolation-filters:sRGB;">
      <feFlood
         id="feFlood2241"
         result="flood"
         flood-color="rgb(36,49,189)"
         flood-opacity="0.67451" />
      <feComposite
         id="feComposite2243"
         result="composite1"
         operator="in"
         in2="SourceGraphic"
         in="flood" />
      <feGaussianBlur
         id="feGaussianBlur2245"
         result="blur"
         stdDeviation="2"
         in="composite1" />
      <feOffset
         id="feOffset2247"
         result="offset"
         dy="1.38778e-16"
         dx="1.38778e-16" />
      <feComposite
         id="feComposite2249"
         result="composite2"
         operator="over"
         in2="offset"
         in="SourceGraphic" />
    </filter>
  </defs>
  <g
     style="stroke:none"
     transform="translate(0,61)"
     id="layer1">
    <circle
       r="8.1020546"
       onmouseover=""
       cy="378.56848"
       cx="22.85927"
       id="play2"
       style="pointer-events:all;stroke-width:0.365001;stroke:none;fill-rule:evenodd"
       class="play2" />
    <path
       onmouseover=""
       transform="matrix(0.65068539,0,0,0.65068539,5.479179,240.84813)"
       d="m 32.756415,211.60548 -8.979319,5.18422 v -10.36843 z"
       id="path19"
       style="fill-rule:evenodd;stroke:none;stroke-width:0.365001;stop-color:#000000" />
    <rect
       ry="0"
       rx="0"
       y="378.03143"
       x="46.811066"
       height="1.4608775"
       width="513.13055"
       id="rectDateGizmo"
       style="fill:#ffcc00;fill-rule:evenodd;stroke:none;stroke-width:0.74270439"
       class="play2" />
    <rect
       rx="4.6434426"
       ry="4.4129586"
       y="385.21191"
       x="460.80215"
       height="8.8259172"
       width="99.231041"
       id="rect5018"
       style="fill:url(#cmapGrad);fill-opacity:1;fill-rule:evenodd;stroke:#000000;stroke-width:0.443491;stop-color:#000000" />
    <g
       style="stroke:none"
       id="gizmoDateHandle"
       x="110">
      <path
         onmouseover=""
         d="m 24.130302,359.9433 h 46.970454 c 2.39527,0 4.32359,1.95086 4.32359,4.37412 0,2.42326 -1.92832,4.37412 -4.32359,4.37412 H 49.345878 l -1.670273,9.15776 -1.714438,-9.15776 H 24.130302 c -2.39527,0 -4.323591,-1.95086 -4.323591,-4.37412 0,-2.42326 1.928321,-4.37412 4.323591,-4.37412 z"
         style="pointer-events:all;stop-color:#000000;image-rendering:auto;stroke-width:0.365001;stroke:none;fill-rule:evenodd;fill:#ffcc00"
         id="gizmoDateBubble"
         class="gizmo" />
      <text
         id="gizmoDateText2"
         user-select="none"
         y="366.12405"
         x="47.92844"
         style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:5.61615px;line-height:1.25;letter-spacing:0px;word-spacing:0px;fill:#554400;fill-opacity:1;stroke:none;stroke-width:0.234006"
         xml:space="preserve"
         class="svgtxt"><tspan
           y="366.12405"
           x="47.92844"
           style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-family:'DejaVu Sans';-inkscape-font-specification:'DejaVu Sans';text-align:center;text-anchor:middle;fill:#554400;fill-opacity:1;stroke-width:0.234006;stroke:none"
           id="gizmoDateText">Sat 16, 3 AM</tspan></text>
    </g>
  </g>
  <rect
     transform="rotate(90)"
     ry="0"
     rx="0"
     y="-589.73187"
     x="89.827507"
     height="0.88159215"
     width="116.1299"
     id="rectDepthGizmo"
     style="fill:#554400;fill-rule:evenodd;stroke:#554400;stroke-width:0.26595;stop-color:#000000"
     class="play2" />
  <rect
     y="88.974625"
     x="589.21533"
     height="1.3081919"
     width="2.9019623"
     id="rect525"
     style="opacity:1;fill:#554400;fill-opacity:1;fill-rule:evenodd;stroke:none;stroke-width:0.940876;stop-color:#000000" />
  <rect
     y="108.27399"
     x="589.21533"
     height="1.3081919"
     width="2.9019623"
     id="rect1745"
     style="opacity:1;fill:#554400;fill-opacity:1;fill-rule:evenodd;stroke:none;stroke-width:0.940876;stop-color:#000000" />
  <rect
     y="127.57335"
     x="589.21533"
     height="1.3081919"
     width="2.9019623"
     id="rect1747"
     style="opacity:1;fill:#554400;fill-opacity:1;fill-rule:evenodd;stroke:none;stroke-width:0.940876;stop-color:#000000" />
  <rect
     y="146.87271"
     x="589.21533"
     height="1.3081919"
     width="2.9019623"
     id="rect1749"
     style="opacity:1;fill:#554400;fill-opacity:1;fill-rule:evenodd;stroke:none;stroke-width:0.940876;stop-color:#000000" />
  <rect
     y="166.17207"
     x="589.21533"
     height="1.3081919"
     width="2.9019623"
     id="rect1751"
     style="opacity:1;fill:#554400;fill-opacity:1;fill-rule:evenodd;stroke:none;stroke-width:0.940876;stop-color:#000000" />
  <rect
     y="185.47144"
     x="589.21533"
     height="1.3081919"
     width="2.9019623"
     id="rect1753"
     style="opacity:1;fill:#554400;fill-opacity:1;fill-rule:evenodd;stroke:none;stroke-width:0.940876;stop-color:#000000" />
  <rect
     y="204.7708"
     x="589.21533"
     height="1.3081919"
     width="2.9019623"
     id="rect1755"
     style="opacity:1;fill:#554400;fill-opacity:1;fill-rule:evenodd;stroke:none;stroke-width:0.940876;stop-color:#000000" />
  <g
     id="gizmoDepthHandle">
    <path
       d="m 546.32994,84.470691 h 30.65138 c 1.92256,0 3.47033,1.470942 3.47033,3.298075 l 8.90745,1.538564 -8.90745,1.505089 c 0,1.827134 -1.54777,3.298075 -3.47033,3.298075 h -30.65138 c -1.92256,0 -3.47033,-1.470941 -3.47033,-3.298075 v -3.043653 c 0,-1.827133 1.54777,-3.298075 3.47033,-3.298075 z"
       style="pointer-events:all;stop-color:#000000;stroke-width:0.689306;stroke:none;fill-rule:evenodd;fill:#ffcc00;opacity:1"
       class="gizmo"
       id="gizmoDepthBubble" />
    <text
       id="gizmoDepthText"
       y="91.544289"
       x="573.72479"
       style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:6.43312px;line-height:1.25;text-align:center;letter-spacing:0px;word-spacing:0px;text-anchor:middle;fill:#000000;fill-opacity:1;stroke:none;stroke-width:0.482484"
       xml:space="preserve"><tspan
         y="91.544289"
         x="561.85431"
         style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:6.43312px;font-family:'DejaVu Sans';-inkscape-font-specification:'DejaVu Sans';text-align:center;text-anchor:middle;stroke-width:0.482484"
         id="gizmoDepthText2">Surface</tspan></text>
  </g>
  <rect
     ry="4.1256037"
     y="-5.5980129"
     x="278.60779"
     height="9.510129"
     width="128.71243"
     id="rect3797"
     style="fill:#aad400;stroke:none;stroke-width:0.61" />
  <text
     id="textDate"
     y="1.6582582"
     x="282.46436"
     style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:7.959px;line-height:1.25;text-align:end;letter-spacing:0px;word-spacing:0px;text-anchor:end;fill:#222b00;fill-opacity:1;stroke:none;stroke-width:0.331625"
     xml:space="preserve"><tspan
       y="1.6582582"
       x="341.93777"
       style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-family:sans-serif;-inkscape-font-specification:sans-serif;text-align:center;text-anchor:middle;fill:#222b00;stroke-width:0.331625"
       id="textDate2">       </tspan></text>
  <rect
     y="440.05548"
     x="46.876831"
     height="2.4570351"
     width="1.2513598"
     class="dateTick"
     id="dateTick"
     style="opacity:0.992256;fill:#ffcc00;fill-rule:evenodd;stroke:none;stroke-width:7.26215;stop-color:#000000;fill-opacity:0.55627108" />
  <rect
     ry="4.1256037"
     y="-5.1944618"
     x="466.48795"
     height="9.510129"
     width="128.71243"
     id="rectCoords"
     style="fill:#e3dbdb;stroke:none;stroke-width:0.61" />
  <text
     id="textCoords"
     y="2.0617959"
     x="470.34454"
     style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:7.959px;line-height:1.25;text-align:end;letter-spacing:0px;word-spacing:0px;text-anchor:end;fill:#222b00;fill-opacity:1;stroke:none;stroke-width:0.331625"
     xml:space="preserve"><tspan
       y="2.0617959"
       x="529.8175"
       style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-family:sans-serif;-inkscape-font-specification:sans-serif;text-align:center;text-anchor:middle;fill:#222b00;stroke-width:0.331625"
       id="textCoords2">   </tspan></text>
  <rect
     class="svgbutton"
     style="pointer-events:all;opacity:0.601525;fill:#ffcc00;fill-opacity:0.78039;fill-rule:evenodd;stroke:none;stroke-width:0;stop-color:#000000;stroke-dasharray:none"
     id="btnPoint"
     width="20.425196"
     height="20.425196"
     x="573.73987"
     y="12.166425"
     ry="5.2242203" />
  <circle
     style="opacity:1;fill:none;fill-opacity:0.556271;fill-rule:evenodd;stroke:#333333;stroke-width:0.77533;stroke-dasharray:none;stop-color:#000000"
     id="path934"
     cx="583.95245"
     cy="22.379021"
     r="5.3250775" />
  <path
     style="fill:none;stroke:#000000;stroke-width:0.688386px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1"
     d="M 583.82383,14.185651 V 30.666992"
     id="path1544" />
  <path
     style="fill:none;stroke:#000000;stroke-width:0.688386px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1"
     d="M 592.0645,22.426321 H 575.58315"
     id="path1546" />
  <rect
     class="svgbutton"
     style="pointer-events:all;opacity:0.601525;fill:#ffcc00;fill-opacity:0.776443;fill-rule:evenodd;stroke:none;stroke-width:0;stop-color:#000000;stroke-dasharray:none"
     id="btnLayer"
     width="20.425196"
     height="20.425196"
     x="573.73987"
     y="34.19479"
     ry="5.2242203" />
  <rect
     style="opacity:1;fill:#b3b3b3;fill-opacity:1;fill-rule:evenodd;stroke:#1a1a1a;stroke-width:0.868026;stroke-dasharray:none;stop-color:#000000"
     id="rect2386"
     width="9.5876312"
     height="7.271852"
     x="543.57104"
     y="55.905323"
     ry="0"
     transform="matrix(1,0,0.60288906,0.79782503,0,0)" />
  <rect
     style="opacity:1;fill:#b3b3b3;fill-opacity:1;fill-rule:evenodd;stroke:#1a1a1a;stroke-width:0.868026;stroke-dasharray:none;stop-color:#000000"
     id="rect2384"
     width="9.5876312"
     height="7.271852"
     x="545.65186"
     y="52.45401"
     ry="0"
     transform="matrix(1,0,0.60288906,0.79782503,0,0)" />
  <rect
     style="opacity:1;fill:#ffffff;fill-opacity:1;fill-rule:evenodd;stroke:#1a1a1a;stroke-width:0.868026;stroke-dasharray:none;stop-color:#000000"
     id="rect2382"
     width="9.5876312"
     height="7.271852"
     x="547.73267"
     y="49.002697"
     ry="0"
     transform="matrix(1,0,0.60288906,0.79782503,0,0)" />
  <text
     id="txtUnits"
     y="452.95081"
     x="474.11829"
     style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:6.35px;line-height:1.25;letter-spacing:0px;word-spacing:0px;mix-blend-mode:difference;fill:#000000;fill-opacity:1;stroke:none;stroke-width:0.264583"
     xml:space="preserve"><tspan
       y="452.95081"
       x="458.99673"
       style="font-style:normal;font-variant:normal;font-weight:bold;font-stretch:normal;font-family:'DejaVu Sans';-inkscape-font-specification:'DejaVu Sans';text-align:end;text-anchor:end;fill:#000000;stroke:none;stroke-width:0.264583"
       id="tspan4288">MPH</tspan></text>
  <text
     id="textMinVal"
     y="458.84293"
     x="473.73685"
     style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:3.26912px;line-height:1.25;text-align:center;letter-spacing:0px;word-spacing:0px;text-anchor:middle;mix-blend-mode:difference;fill:#000000;fill-opacity:1;stroke:none;stroke-width:0.136213"
     xml:space="preserve"><tspan
       y="458.84293"
       x="463.16568"
       style="font-style:normal;font-variant:normal;font-weight:bold;font-stretch:normal;font-family:'DejaVu Sans';-inkscape-font-specification:'DejaVu Sans';text-align:center;text-anchor:middle;fill:#000000;stroke:none;stroke-width:0.136213"
       id="textMinVal2">-10</tspan></text>
  <text
     id="textMaxVal"
     y="458.84293"
     x="568.89685"
     style="font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:3.26912px;line-height:1.25;text-align:center;letter-spacing:0px;word-spacing:0px;text-anchor:middle;mix-blend-mode:difference;fill:#000000;fill-opacity:1;stroke:none;stroke-width:0.136213"
     xml:space="preserve"><tspan
       y="458.84293"
       x="558.32568"
       style="font-style:normal;font-variant:normal;font-weight:bold;font-stretch:normal;font-family:'DejaVu Sans';-inkscape-font-specification:'DejaVu Sans';text-align:center;text-anchor:middle;fill:#000000;stroke:none;stroke-width:0.136213"
       id="textMaxVal2">10</tspan></text>
</svg>



    </div>


</div>

<script type="text/python" src="main.py">

</script>




</body>
</html>
