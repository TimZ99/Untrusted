# Untrusted
My Untrusted Solutions -> https://alexnisnevich.github.io/untrusted/
## 1
```Leave empty```

## 2
```/* ```

```*/ ```

## 3
```
for (y = 12; y <= map.getHeight() - 3; y++) {
  map.placeObject(5, y, 'block');
  map.placeObject(map.getWidth() - 5, y, 'block');
  }
for (x = 1; x <= map.getWidth() - 5; x++) {
  map.placeObject(x, 10, 'block');
  map.placeObject(x, map.getHeight() - 3, 'block');
}
```

## 4
```
map.placeObject(map.getWidth() - 5, 10, 'exit');
```

## 5
```
map.setSquareColor(x, y, '#fff');
```

## 6
```
map.placeObject(map.getWidth()-11, 11, 'block');
map.placeObject(map.getWidth()-12, 11, 'block');
map.placeObject(map.getWidth()-12, 12, 'block');
```
