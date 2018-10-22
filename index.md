---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
---
What is the Geodynamic World Builder? 
====================================
This c++ library (with wrappers for c and fortran) allows you to easily set up 
models of intermidary complexity:
 ```js
"version":"0.1",
"coordinate system":{"spherical":{"depth method":"begin segment"}},
"cross section":[[0,0],[10,0]],
"surface objects":
{
  "oceanic plate":{"name":"oceanic plate", "coordinates":[[-1,-1],[11.5,-1],[11.5,1],[-1,1]],
                   "temperature model":{"name":"plate model", "depth":95e3, "spreading velocity":0.005, "ridge points":[[1,-1],[1,1]]},
                   "composition model":{"name":"constant layers", "layers":[{"composition":0, "thickness":10e3},{"composition":1, "thickness":85e3}]}},

  "continental plate":{"name":"continental plate", "coordinates":[[11.5,-1],[21,-1],[21,1],[11.5,1]],
                   "temperature model":{"name":"linear", "depth":95e3},
                   "composition model":{"name":"constant layers", "layers":[{"composition":2, "thickness":30e3},{"composition":3, "thickness":65e3}]}},

  "mantle layer":{"name":"upper mantle", "top depth":95e3, "coordinates":[[-1,-1],[21,-1],[21,1],[-1,1]],
                   "temperature model":{"name":"none"},
                   "composition model":{"name":"constant", "depth":565e3, "composition":4}},

  "mantle layer":{"name":"lower mantle", "top depth":660e3, "coordinates":[[-1,-1],[21,-1],[21,1],[-1,1]],
                   "temperature model":{"name":"none"},
                   "composition model":{"name":"constant", "depth":500e3, "composition":5}},

  "subducting plate":{"name":"Subducting plate", "coordinates":[[11.5,-1],[11.5,1]], "reference point":[20,0],
    "segments":
    {
      "all":[{"length":200e3, "thickness":[95e3], "angle":[0,45]}, {"length":200e3, "thickness":[95e3], "angle":[45]},
             {"length":200e3, "thickness":[95e3], "angle":[45,0]},{"length":100e3, "thickness":[95e3], "angle":[0]}]
    },
    "temperature model":{"name":"plate model", "density":3300, "plate velocity":0.01 },
    "composition model":{"name":"constant layers", "layers":[{"composition":0, "thickness":10e3},{"composition":1, "thickness":85e3}]}}
}
```
