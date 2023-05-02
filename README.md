# Drag Camera Script for FiveM

This script provides a custom camera control functionality for FiveM, allowing users to drag and rotate the camera around a target entity with the mouse. Users can also zoom in and out using the scroll wheel. This script is useful for inspecting and observing objects in-game from different angles.

## Features

- Drag the camera with the mouse to rotate around the target entity
- Zoom in and out with scroll wheel or keys
- Disable player and camera movement when the drag camera is active
- Show instructional buttons for zoom controls

## Installation

1. Create a new folder in your FiveM server's resources directory, e.g., dragcam.
2. Copy the provided Lua script file into the new folder.
3. Add the resource to your server.cfg file by adding the line: ensure dragcam.

## Usage

This script exports two functions, `startDragCam` and `stopDragCam`, which can be called by other resources to enable or disable the drag camera functionality.

### startDragCam

`startDragCam(entity, radiusOptions)`

- entity: The target entity around which the camera should rotate.
- radiusOptions: An optional table with the following keys:
  - initial: The initial distance from the camera to the entity (default: 5.0).
  - min: The minimum allowed distance from the camera to the entity (default: 2.5).
  - max: The maximum allowed distance from the camera to the entity (default: 10.0).
  - scrollIncrements: The distance the camera should move when the zoom controls are used (default: 0.5).

### stopDragCam

`stopDragCam()`

This function disables the drag camera functionality and returns control to the default camera.

## Example

```lua
local dragcamResource = 'dragcam' -- Change this to the name of your dragcam resource

-- Start the drag camera
exports[dragcamResource]:startDragCam(someEntity, {initial = 5.0, min = 2.5, max = 10.0, scrollIncrements = 0.5})

-- Stop the drag camera
exports[dragcamResource]:stopDragCam()
```
