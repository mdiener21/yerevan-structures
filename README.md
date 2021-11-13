# Yerevan, Armenia Bridges


## Getting Openstreetmap bridges

### Overpass API openstreetmap

[turbo api overpass](https://overpass-turbo.eu/)
Paste this query into the query window and bingo you see bridges

```
/*
The original search was:
“bridge=yes or tunnel=yes”
*/
[out:json][timeout:25];
// gather results
(
  // query part for: “bridge=yes”
  node["bridge"="yes"]({{bbox}});
  way["bridge"="yes"]({{bbox}});
  // query part for: “tunnel=yes”
  node["tunnel"="yes"]({{bbox}});
  way["tunnel"="yes"]({{bbox}});
);
// print results
out body;
>;
out skel qt;
```
