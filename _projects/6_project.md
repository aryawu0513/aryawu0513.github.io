---
layout: page
title: Photon Mapping
description: Final Project for MIT 6.4400 Computer Graphics
img: assets/img/photon.jpg
importance: 2
category: course projects
---

<div class="container">
    <div class="row mt-4">
        <div class="col-md-12">
            <p>Previously in the course, we have studied and implemented a simple ray-tracing algorithm. Ray tracing, while effective for direct illumination, has its limitations when it comes to capturing intricate global illumination effects such as indirect lighting. Photon mapping provides a more realistic representation of how light interacts with surfaces in a scene. We chose to implement photon mapping upon our basic ray tracer on our self-created cornell box scene of hittables.</p>
        </div>
    </div>
    
    <div class="row mt-4">
        <div class="col-md-6">
            <img src="https://lh7-us.googleusercontent.com/3OFHAR2q74_nexodlObtUSTAuXZiC3_hQ77Oq1rK_rKXtEDcvabGPGRCQt12lH2jF5Tq0ky2tr-kpmXaYmpGmi-xPd4wVBrl7A4473OyvQuPPZs8VHEOAkNGpqW-oxIZsHG0NilJOgcQJ-zI0V-roYY" class="img-fluid rounded z-depth-1" alt="Cornell Box Scene (without photon map)">
            <p class="caption">Fig 1: Cornell box scene (without photon map)</p>
        </div>
        
        <div class="col-md-6">
            <img src="https://lh7-us.googleusercontent.com/a5KNz_8J1oX22zDZH5_Ib3K0ebVMp6IVtpgqBWfLpqk2PIwPBybd5qLOwcYPILjKyYzI11WWPAWAyXP3KspfY6619IIrWG4shSI-gDCT5RNAJpR25ibmuzPp8JUJexdAP-Mlt-gIcVbyNSXbN55RyME" class="img-fluid rounded z-depth-1" alt="Cornell Box Scene with Shadow Enabled">
            <p class="caption">Fig 2: Cornell box scene with shadow enabled</p>
        </div>

        <div class="col-md-12">
            <p>We followed the standard two-pass algorithm of photon mapping, first generating photons, and then rendering the scene using the generated photon map.</p>
            <p>Photons are emitted and traced through the scene recursively, with their positions, directions, and weights updated based on their hit records with the scene. The direction is updated by taking into account the behavior of reflection and refraction. Following the paper, we implemented Russian Roulette to terminate photon paths probabilistically. For faster rendering, we used the kd-tree structure to store our photon map.</p>
        </div>

        <div class="col-md-6">
            <img src="https://lh7-us.googleusercontent.com/_zQyNgmF07zJbJyhEWoBGdjp1uPW_E_9NVKoqKHvcI8Pqpyq3hR9GMni0rnZ5GdQOYCTjU1Q0eqiVo1dN70q6beBvu59WVDWqEqlIbPBx622A5LKoh8TH1IXFZwgRROhHYjU9JdXGgNVKV_O98oY3dk" class="img-fluid rounded z-depth-1" alt="100,000 photons and k=10,000 point cloud of photon map with caustics and BRDF">
            <p class="caption">Fig 9 (Left): 100,000 photons and k=10,000 point cloud of photon map with caustics and BRDF</p>
        </div>

        <div class="col-md-6">
            <img src="https://lh7-us.googleusercontent.com/LKN_LYeppIL7XbFgc2LrTpFNn2ZIlN3SKOaev1J31QnXLCdOVQUuIrJ3gdORt1w75RbF30D67_7kvTe11-ZQjs55ARkqWk4PYq-SShWILLCDnaBVcQ-HzTk2YGl5gtFw7T9tvDRKTAUD86proM3M8Xc" class="img-fluid rounded z-depth-1" alt="5,000,000 photons and k=10,000 point cloud of photon map with caustics and BRDF">
            <p class="caption">Fig 10 (Right): 5,000,000 photons and k=10,000 point cloud of photon map with caustics and BRDF</p>
        </div>

        <div class="col-md-12">
            <p>With the generated photon map, we moved on to the second-pass, which is rendering by shooting rays from the camera into the scene to simulate the interaction of light with surfaces. Each pixel in the image corresponds to a ray that is cast into the scene, and the resulting color is determined by the estimate reflected radiance using the precomputed photon map.</p>
            <p>We sum the radiance of the k nearest photons with weights taking into account the material’s BRDF and the flux of the photon. We calculate the direct and indirect illumination using our global map, as well as the specular reflection using our caustic map. The meaningful difference is we applied cone filtering to assign a weight to each photon based on the distance between the point of intersection and the photon, this intensifies the caustic effects at the point of intersection.</p>
            <p>The algorithm outputs the final color by adding the reflected radiance, direct illumination, and results from caustics. We achieved a combination of caustics, direct illumination, and indirect illumination, providing a realistic representation of light interactions within the scene.</p>
        </div>

        <div class="col-md-6">
            <img src="https://lh7-us.googleusercontent.com/J7cNr_FL4TsgkpPy19g9NxPahfQvrqj6FlcHG7yuab6D7nQQ9x3-SKIust2RIjPgh5Lj-ewgLeR_kqygJ9t75RQpuXuXwlra0yC8QuFUdTAXmV3FD4Oy2YHUR0h6zPuR5rFbSwGHpTcvMH_fG32V6aM" class="img-fluid rounded z-depth-1" alt="Cornell Box with different materials, with 100,000 photons and k=10,000">
            <p class="caption">Fig 10 (Left): Cornell Box with different materials, with 100,000 photons and k=10,000</p>
        </div>

        <div class="col-md-5">

            {% include figure.liquid loading="eager" path="assets/img/photon.jpg" title="Example Image" class="img-fluid rounded z-depth-1" %}

            <p class="caption">Fig 11 (Right): Cornell Box with 5,000,000 photons and k=10,000</p>
        </div>
    </div>

    <div class="row mt-4">
        <div class="col-md-12">
            <p>We successfully implemented photon mapping for global illumination by building upon our existing ray tracer from assignment 4. The resulting rendering of the Cornell box shows a clear effect of reflection, demonstrating the successful integration of photon mapping for realistic reflection effects in our ray tracer. We also leveraged our implemented kd-tree data structure and OpenMP parallel programming to speed up the ray tracing by a considerable amount.</p>

        </div>
    </div>

</div>
