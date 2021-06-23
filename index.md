---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
---
What is the Geodynamic World Builder?
====================================
This c++ library (with wrappers for C, Fortran and Python) allows you to easily set up
models of intermediate complexity. This code is enough to generate the model in the pictures seen below:
 ```js
{
  "version":"0.5",
  "cross section":[[0,200e3],[100e3,200e3]],
  "features":
  [
    {"model":"mantle layer", "name":"upper mantle", "min depth":100e3, "max depth":660e3,
       "coordinates":[[0,0],[0,1000e3],[2000e3,1000e3],[2000e3,0]],
       "composition models":[{"model":"uniform", "compositions":[4]}]},

    {"model":"oceanic plate", "name":"Overriding plate", "max depth":100e3,
       "coordinates":[[0,0],[0,1000e3],[1500e3,1000e3],[1600e3,350e3],[1500e3,0]],
       "temperature models":[{"model":"plate model", "max depth":100e3, "spreading velocity":0.01,
                              "ridge coordinates":[[400e3,-1],[-100e3,2000e3]]}],
       "composition models":[{"model":"uniform", "compositions":[0], "max depth":100e3}]},

    {"model":"oceanic plate", "name":"Atlantic Plate", "max depth":100e3,
       "coordinates":[[2000e3,0],[2000e3,1000e3],[1500e3,1000e3],[1600e3,350e3],[1500e3,0]],
       "temperature models":[{"model":"linear", "max depth":100e3}],
       "composition models":[{"model":"uniform", "compositions":[3], "max depth":50e3},
                             {"model":"uniform", "compositions":[1], "min depth":50e3}]},

    {"model":"subducting plate", "name":"Slab",
       "coordinates":[[1500e3,1000e3],[1600e3,350e3],[1500e3,0]],
       "dip point":[0,0],
       "segments":[{"length":300e3, "thickness":[100e3], "angle":[0,60],
                   "composition models":[{"model":"uniform", "compositions":[3], "max distance slab top":50e3},
                                        {"model":"uniform", "compositions":[2], "min distance slab top":50e3}]},
                   {"length":500e3, "thickness":[100e3], "angle":[60,20]}],
       "sections":[
         {"coordinate":0,
        "segments":[{"length":300e3, "thickness":[100e3], "angle":[0,60]},
                    {"length":400e3, "thickness":[100e3,50e3], "angle":[60]}],
         "composition models":[{"model":"uniform", "compositions":[1]}]}
       ],
       "temperature models":[{"model":"plate model", "density":3300, "plate velocity":0.02 }],
       "composition models":[{"model":"uniform", "compositions":[2], "max distance slab top":100e3}]}
  ]
}
```
This is a 3D view of the model defined by the code above. The top picture shows the different compositional fields and the bottom picutre show the temperature field.
![RFM-12-sections-hires_c1_T](https://user-images.githubusercontent.com/7631629/116262023-7d989d80-a778-11eb-8f6e-fd84111a588a.png)


This crosssection is made by providing 2D coordinates to the world builder. Like the picture above, the top picture shows the different compositional fields and the bottom picture show the temperature field.
![RFM-11-2D_c1_T](https://user-images.githubusercontent.com/7631629/116261338-d451a780-a777-11eb-82e0-5225c7b884ea.png)


