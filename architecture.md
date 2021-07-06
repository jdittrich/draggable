## Draggable Class 
What it does:
Inherits from: 
Parameters:
Return: 


## Sensor
What it does: While its descendants implement the parts specific to the input type, the sensor base class
implements the standard methods that all sensors need, which is e.g. the custom drag events of draggable.js
The custom events seem to be syntehtic DOM events? (see trigger?)

Inherits from: --

Parameters: Containers, options

Methods:
trigger: gets an container and an customevent?, dispatches the event on the container, adds the customevent to event.detail. 

### Mouse Sensor
What it does: 
"This sensor picks up native browser mouse events and dictates drag operations"
It attaches mouse-event listeners to the document and triggers the drag events of draggable.js
via the methods of the parent class, Sensor. 

Inherits from: Sensor

Parameters: Containers, options

Methods:

## Droppable

What it does: It kinda replaces Draggable so that you now can also define a 'dropzone' property passed to Droppable. 

Inherits from: Draggable (since it basically extends it with the ability to define dropzone elements)

Parameters: Containers, options (particularly "dropzones")    

Methods:

# Plugins

How do plugins communicate with each other or core? 
Probably only events

## Mirror 

[Link](./src/Draggable/Plugins/Mirror/Mirror.js)

What it does: Seems to provide an element that "mirrors" (I'd rather say visually proxies) the dragged source.  
It "gets active" on dragstart (it subscribes to the event internally).

Inherits from: Abstract Plugin

