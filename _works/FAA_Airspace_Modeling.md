---
title: FAA Airspace Modeling
description: Utilizing data from the FAA, airspace protection surfaces are modeled and made available to project teams.
category: FME Flow
date: 2024-01-10 08:01:35 +0300
client: 
role: Tool Developer
image: '/images/Aeronautical.png'
image_caption: 'Part 77 Surfaces'
---

Project teams in the energy sector (as well as other sectors) are alwasy in need of knowing how tall structures can be without being a FAA Obstruction. Utilizing data from the FAA, airspace protection surfaces are modeled and made available to project teams. This data is updated every 28 days (4 weeks) by the FAA.  The tool was developed to download the newest data and generate the Part 77 surfaces for every airport in the FAA database. FME Flow was utilized to automatme this so that the project teams always had access to the most up-to-date information possible.

<div class="gallery-box">
  <div class="gallery">
    <img src="/images/FAA_DEM.png" loading="lazy" alt="Project">
    <img src="/images/Aeronautical.png" loading="lazy" alt="Project">
    <img src="/images/FAA_LAS.png" loading="lazy" alt="Project">
  </div>
  <em></em>
</div>

Additional tools were developed to model the TERPS (instrument approaches) for airports in addition to the Part 77 surfaces.  By creating all of these surfaces in 3D we can calculate an accurate max structure height to either eliminate the need to file with the FAA or to stay under the obstruction standards.  By staying under the obstruction standards the project minimizes the risk of needing to implement marking and lighting of strucgtures.

This tool can be further refined by the introduction of high accuracy ground survey in the form of LiDAR scans.  