Gandhi Sagar Renewable Nexus - project files

1. gandhi-sagar-nexus.html  (the whole website + 3D model, single file)
   Double-click to open in Chrome/Edge/Firefox. Needs internet once to load three.js from a CDN.
2. three.min.js  (three.js r128, for offline use)
   Keep it in the same folder as the HTML, then in the HTML change the line
   <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
   to
   <script src="three.min.js"></script>

Notes
- Terrain, layout, costs and capacity factors are schematic/illustrative, not survey or vendor data.
- Existing hydro (about 115 MW) is from general knowledge: verify with MPPGCL.
- Edit costs/tariffs in the Finance tab; zones/positions are in the script (search for "zone(" and "LB=").
