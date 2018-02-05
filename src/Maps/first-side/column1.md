 folium version: 0.5 - Date: January 2018
 
# Initialize a map

```python
m = folium.Map(location=(52.518611, 13.408333), zoom_start=14)
```

Add a for switching between layers
folium.LayerControl().add_to(m)

Making it interactive
```python
from ipywidgets import interact
tiles = [name.strip() for name in """
    OpenStreetMap
    Mapbox Bright
    Mapbox Control Room
    Stamen Terrain
    Stamen Toner
    Stamen Watercolor
    CartoDB positron
    CartoDB dark_matter
    cartodbdark_matter""".strip().split('\n')]

@interact(lat=(-90., 90.), lon=(-180., 180.), tiles=tiles, zoom=(1, 18))
def create_map(lat=52.518611, lon=13.408333, tiles="Stamen Toner", zoom=10):
    return folium.Map(location=(lat, lon), tiles=tiles, zoom_start=zoom)
```

Draw a marker and a circle
```python
folium.Marker([52.518611, 13.408333], popup='<b>Timberline Lodge</b>', icon = folium.Icon(color='green',icon='ok-sign')).add_to(m) 

folium.features.Circle(
    radius=100,
    location=[52.518611, 13.408333],
    popup='The Waterfront',
    color='crimson',
    fill=True,
    fill_color='#3186cc'
).add_to(m)
```


