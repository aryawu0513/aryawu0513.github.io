---
layout: page
title: User-centered Design Using AI
description: MIT D-Lab
img: assets/img/dlab.jpg
importance: 3
category: research projects
---

<a href="https://www.researchgate.net/publication/375813743_Form_Attributes_to_Measure_and_Understand_Aesthetic_Preferences" target="_blank">Form Attributes to Measure and Understand Aesthetic Preferences</a>

<column-set gutter="0rem" mobile-hide-empty="false" mobile-stack="true">
    <column-unit slot="0" span="3"></column-unit>
    <column-unit slot="1" span="9">
        <br>
        Generative Design Tools empowered by artificial intelligence have been increasingly in use in industry and research. These tools use quantitative inputs to generate designs optimized for performance. We are interested in understanding how qualitative objectives, such as aesthetics based on user preferences, are balanced with quantitative objectives, as represented by our multi-objective optimization (MOO) tool.
        <br>
        <br>
        I'm responsible for maintaining the Rhino+Grasshopper Generative Design Tool, constructing and running in-lab experiments, and assisting in data analysis.
        <br>
        <br>
        Our experiment builds upon the verified assumption that individuals' aesthetic preferences carry through different forms of objects. For example, users' aesthetic preferences of canopies are carried on to vases. We categorized the forms into four categories: Long/Short, Wide/Narrow, Curved/Angular, and Complex/Simple. Each canopy is associated in form to a vase image that we constructed.
        <br>
                {% include figure.liquid loading="eager" path="assets/img/dlab0.png" title="Example Image" class="img-fluid rounded z-depth-1" %}
        <br>
        Designers are given the task of designing canopies according to the cafe owner's preference, which is given to them in the form of vases they like and vases they dislike. By leveraging Grasshopper, the designer is free to make changes to the canopy by sliding the slide bars that controls the form, such as length, number of supports, curvature, tip, and anchor points. Each canopy being designed has their associated performance index. Two numbers are reported to the user, the first is the current shaded area in ft^2 and the weight in kg. The second number is the normalization of the current performance with respect to the best possible performance.

        <br>
        <div style="display: flex; align-items: stretch;">
            <!-- Vertical Image on the Left -->
            <div style="flex: 1; padding-right: 10px;">
                {% include figure.liquid loading="eager" path="assets/img/dlab1.png" title="Vertical Image" class="img-fluid rounded z-depth-1" %}
            </div>
            <!-- Two Vertical Images Stacked on the Right -->
            <div style="flex: 1; display: flex; flex-direction: column;">
                <div style="flex: 1; margin-bottom: 10px;">
                    {% include figure.liquid loading="eager" path="assets/img/dlab3.png" title="Vertical Image 1" class="img-fluid rounded z-depth-1" %}
                </div>
                <div style="flex: 1;">
                    {% include figure.liquid loading="eager" path="assets/img/dlab2.png" title="Vertical Image 2" class="img-fluid rounded z-depth-1" %}
                </div>
            </div>
        </div>
        Each Designer is given two tasks, each round takes 30 minutes. The designer first design freely and rely on their own judgement, and then in the second round, a Multi-objective optimization tool is introduced to assist the design process. MOO will explore 100 possible designs and will capture the top 20 designs. These 20 optimized designs are either the best in terms of shaded area, the best in terms of weight, or somewhere in between for both objectives. At the end, the users are asked to provide the top three design from both rounds, with answers on their process of balancing between the aesthetic looks of the canopy and the performance index. We perform data analysis to understand how incorporating aesthetic objectives in generative design affect the design process and design outcomes.
    </column-unit>

</column-set>
