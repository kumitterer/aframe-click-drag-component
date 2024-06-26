# aframe-click-drag-component

A Click & Drag component for [A-Frame](https://aframe.io). This is a fork of
the original [aframe-click-drag-component](https://github.com/jesstelford/aframe-click-drag-component)
to make it work in current versions of A-Frame (tested with 1.5.0).

Entities with the `click-drag` component can be click and dragged around the 3D
scene. Even works whle the camera is moving or rotating!

### Events

**dragstart**

Emitted with the following info:

- `offset: {x, y, z}` - The offset from entity center to drag position.
- `depth` - the perpendicular distance from the screen to align the entity while
  dragging
- `clientX` - the mouse event's `clientX` value
- `clientY` - the mouse event's `clientY` value

**dragmove**

Emitted with the following info:

- `nextPosition: {x, y, z}` - The next world position of the entity.
- `clientX` - the mouse event's `clientX` value
- `clientY` - the mouse event's `clientY` value

**dragend**

Emitted with the following info:

- `offset: {x, y, z}` - The offset from entity center to drag position.
- `velocity: {x, y, z}` - The smoothed velocity of the entity at dragend time.
- `depth` - the perpendicular distance from the screen to align the entity while
  dragging
- `clientX` - the final mouse event's `clientX` value
- `clientY` - the final mouse event's `clientY` value

### Applying click-drag conditionally

You can conditionally apply `click-drag` behaviors by specifying an `enabled`
attribute in your `click-drag` property:

```javascript
...
<a-sphere click-drag="enabled: false" position="0 1.25 -1" radius="1.25" color="#EF2D5E"></a-sphere>
...
```

### Installation

#### Browser

Use directly from the unpkg CDN:

```html
<head>
  <script src="https://aframe.io/releases/1.5.0/aframe.min.js"></script>
  <script src="https://unpkg.com/@kumitterer/aframe-click-drag-component"></script>
  <script>
    registerAframeClickDragComponent(window.AFRAME);
  </script>
</head>

<body>
  <a-scene>
    <a-sphere
      click-drag
      position="0 1.25 -5"
      radius="1.25"
      color="#EF2D5E"
    ></a-sphere>
    <a-camera look-controls-enabled="false"></a-camera>
  </a-scene>
</body>
```

#### npm

Install via npm:

```bash
npm install @kumitterer/aframe-click-drag-component
```

Then register and use.

```javascript
import aframe from "aframe";
import registerClickDrag from "@kumitterer/aframe-click-drag-component";
registerClickDrag(aframe);
```
