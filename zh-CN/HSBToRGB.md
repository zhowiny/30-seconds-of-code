---
title: HSB 转 RGB(HSB to RGB)
tags: math
expertise: intermediate
cover: blog_images/houses-rock-sea.jpg
firstSeen: 2020-09-18T14:25:07+03:00
lastUpdated: 2020-09-18T14:25:07+03:00
---

### 将 HSB 颜色元组转换为 RGB 格式。
> Converts a HSB color tuple to RGB format.

- 使用 [HSB 到 RGB 转换公式](https://en.wikipedia.org/wiki/HSL_and_HSV#HSV_to_RGB) 转换为适当的格式。
- 输入参数的范围是H: [0, 360], S: [0, 100], B: [0, 100]。
- 所有输出值的范围是 [0, 255]。

```js
const HSBToRGB = (h, s, b) => {
  s /= 100;
  b /= 100;
  const k = (n) => (n + h / 60) % 6;
  const f = (n) => b * (1 - s * Math.max(0, Math.min(k(n), 4 - k(n), 1)));
  return [255 * f(5), 255 * f(3), 255 * f(1)];
};
```

```js
HSBToRGB(18, 81, 99); // [252.45, 109.31084999999996, 47.965499999999984]
```
