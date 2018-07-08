---
layout: post
title:  "What is the Geodynamic World Builder?"
date:   2018-07-08 21:44:58 +0200
categories: about
---

This c++ library (with wrappers for c and fortran) allows you to easily set up 
models of intermidary complexity:
{% highlight javascript %}
{
  "Cross section": [[100e3,100e3],[400e3,500e3]],
  "Coordinate system":{"name":"cartesian"},
  "Surface rotation point": ["165e3","166e3"],
  "Surface rotation angle": "0",
  "Minimum parts per distance unit": 5,
  "Minimum distance points": 1e-5,
  "Surface objects":{ 
    "Continental plate":{"name":"Carribean","coordinates":[[-1e3,500e3],[500e3,500e3],[500e3,1000e3],[-1e3,1000e3]],
                         "temperature submodule":{"name":"constant", "depth":250e3, "temperature":150},
                         "composition submodule":{"name":"none"}},
    "Continental Plate":{"name":"Rest", "coordinates":[[2000e3,2000e3],[1000e3,2000e3],[1000e3,1000e3],[2000e3,1000e3]],
                         "temperature submodule":{"name":"constant", "depth":250e3, "temperature":20},
                         "composition submodule":{"name":"constant", "depth":250e3, "composition":2}},
     "Continental plate":{"name":"Carribean2","coordinates":[[-1e3,500e3],[500e3,500e3],[500e3,1000e3],[-1e3,1000e3]],
                          "temperature submodule":{"name":"none", "depth":250e3, "temperature":150},
                          "composition submodule":{"name":"constant", "depth":250e3, "composition":3}}
  }
}
{% endhighlight %}
