# Abundance-coffee
zZzZzZZzzZzzzzz

![buh](https://github.com/nicolasbaez/Abundance-coffee/blob/main/xp050.gif)
```javascript
a = 0.01;
b = 99;
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = 0;
draw = (_) => {
  rotateX(k * 0.1);
  clear();
  for (i = 0; i < 3; i += a) {
    x = map(i, 0, 3, -200, 200);
    y = map(sin(i + k), -1, 1, -b, b);
    z = map(cos(i + k), -1, 1, -b, b);
    stroke(noise(x * a, y * a, z * a) * 255);
    n = noise(x * a, y * a) * b;
    line(x, y - n, z, x, y + n, z);
  }
  if (k == 0) saveGif("xp050.gif", 1256, { delay: 0, units: "frames" });
  k += 0.05;
};
