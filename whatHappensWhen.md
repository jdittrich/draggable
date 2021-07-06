## Drag Drop
* User mousedown
* The `[onMouseDown](event)` in [mouse Sensor](./src/Draggable/Sensors/MouseSensor/MouseSensor.js) is called
  * [Closest container](./src/shared/utils/closest/closest.js) (container=an element that can hold draggable elements) to fill `container` which is then written to `currentContainer` 
  TODO: When is container defined?
  * Note: the events work with `this` properties quite a bit: `this` is the draggable-object itself in the event handlers, as they are `.bind(this)` in the [Draggable.js](./src/Draggable/Draggable.js) constuctor.
  * activates [onDistanceChange](event) (how?)
    * When *"both delay and distance requirements are met"*, the `[onDistanceChange](event)` removes itself and calls `this.[startDrag]()`
* `this.[startDrag]()` takes `this.currentContainer` and `this.startEvent` (remember, this is the draggable object) and creates a new `SensorEvent.DragStartSensorEvent(` `this.trigger(currentContainer, dragstartEvent)`. (remember, [trigger/event handling](./src/Emitter/Emitter.js) is actually a separate class, but it is manually proxied to this.trigger, so it is mixin, but not really :) ) 

* Scrollable seems to regularly check if there is a scrollable container under the cursor.

* 