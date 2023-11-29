# Steadfast-mint
aurora

![buh](https://github.com/nicolasbaez/Steadfast-mint/blob/main/xp021.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  clear();
  h = w / 2;
  rotateX(4.9);
  noFill();
  for (j = 0; j > -h; j--) {
    beginShape();
    stroke(0, w, w, map(j, 0, -h, h / 2, 0));
    if (j == 0) stroke(h);
    for (i = -w; i < w; i += 32) {
      t = i * 4;
      curveVertex(i, map(sin(t + w) + cos(t / 4), -1, 1, -h, h), j);
    }
    endShape();
  }
  w -= 0.01;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp021.gif", 512, { delay: 0, units: "frames" });
  }
};
