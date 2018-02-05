# Save the map to html

```python
m.save("mymap.html")
```

Enable lat/lng popovers
```python
m.add_child(folium.LatLngPopup())
```

Place markers on the fly
```python
m.add_child(folium.ClickForMarker(popup='Waypoint'))
```

Add html styletip
```python
map_1.add_child(folium.Marker(
        location=[46.7394, 2.7513],
        popup=folium.Popup(html_info, max_width=450)
        ,icon = folium.Icon(color='blue',icon='ok-sign')
    )
)
```