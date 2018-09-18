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
{
    "cross section": [[100e3,100e3],[400e3,500e3]],
    "coordinate system":{"name":"cartesian"},
    "Surface objects":
    {
     "continental plate":{"name":"Carribean","coordinates":[[-1e3,500e3],[500e3,500e3],[500e3,1000e3],[-1e3,1000e3]],
         "temperature model":{"name":"constant", "depth":250e3, "temperature":150},
         "composition model":{"name":"none"}},

     "continental Plate":{"name":"Rest", "coordinates":[[2000e3,2000e3],[1000e3,2000e3],[1000e3,1000e3],[2000e3,1000e3]],
         "temperature model":{"name":"constant", "depth":250e3, "temperature":20},
         "composition model":{"name":"constant", "depth":250e3, "composition":2}},

     "continental plate":{"name":"Carribean2","coordinates":[[-1e3,500e3],[500e3,500e3],[500e3,1000e3],[-1e3,1000e3]],
         "temperature model":{"name":"none", "depth":250e3, "temperature":150},
         "composition model":{"name":"constant", "depth":250e3, "composition":3}}
    }
}
```
