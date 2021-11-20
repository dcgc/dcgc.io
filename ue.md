---
layout: page
title: Unreal Engine
categories: notes
permalink: /unreal-engine/
---

**Actor** - actor used to represent 3D space.

**Brush Actor** - only used for simple geometric shape (used for prototype levels).

**Static Mesh Actor** - 3D object cannot animate, move around the screen, and doesn’t bend or transform by itself; almost every object in a game is a mesh; static mesh has no moving parts; crafted into objects with high-level of detail (used for final project/design). Most static meshes are created in an external 3d modelling program like Maya, 3dstudiomax, blender and then import it to UE editor.

**Skeleton Mesh Actor** - identify individual parts of the skeleton mesh, and how those parts connect and move with one another.

Even if you populate the mesh, it will not move. You need to enable physics in properties of the object.

**Mass Property** - defines weight of object (less means moves more with interaction; more means moves less with interaction).

**Linear/Angular Damping** - amount of drag applied to the movement of the object (less linear means it will not move far, if more linear means it will move very far) _(less angular means it will not rotate a lot or fast, if more angular means it will rotate a lot)_.  -> Resistencia

**Gravity** - property that defines gravity of object (if it has or not)

**Replication Physics to Autonomous Proxy** - used in MP games

**Meshes can be more complex and detailed than brushes.**
UE brushes copies gets stored multiple times in memory and uses more memory because of it
UE meshes copies get stored once in memory and uses less memory because of it (one instance) (better performance)

Brushes are better suited to make a prototype of a level. Once layout and prototype is finished, you replace brushes (simple forms) with meshes.

**Brush Settings property in Details of Brush > Brush Type:**
**Additive** - add geometry to the level
**Subtractive** - subtract geometry to the level

**Brush Shape** - shape of brush

**Sides Property (Cone, Box, Cylinder)** - the more sides the more flat sides the brush will have, which means it will appear smoother (less geometrical).

**Tesselation Property (Cone, Box, Cylinder)** - it separates, splits triangles into smaller triangles to increase the surface detail of a mesh. Can be a slow effect to render and should be used within reason.

**Hollow Property (Cone, Box, Cylinder)** - it will be hollow inside, with a shell (thick walls) and empty inside.
  Cap Z property - threshold for Z axis.

**You use hollow property for creating rooms or buildings (walls) **

**Sloped Ceiling and Sloped Floor (Stairs)** - makes the beneath part of the stairs and the stairs themselves completely flat (no geometric shape or stairs, respectively), respectively.

**Angle of Curve (Stairs Curved)** - it is do define shape and angle of the curved stairs, it is useful to align it around the column or shape you are trying to connect the stairs to.

**Material Actor** - asset to apply to a surface to make that surface look like it’s made out of a certain substance. They are common to use in brush and static mesh.

A material is made of one or more textures.

**On a material, open Material Editor and click right button with mouse to promote to parameter and change the parameter of the material.**

**Light Actor** - used to represent visible light into the real world.

You don’t use a mesh to produce light for a flashlight object or something similar, you use a light actor to represent the light cast by the flashlight.

**Types of Lights:** 

- **Directional Light** - light from a long distance (shadows are parallel; used primarily for sunlight and moonlight)
- **Point Light** - light that emanates from all directions (light from a lightbulb or from fire)
- **Spot Light** - emit light in the shape of a cone
- **Rect Light** - projects light from a rectangular plane (light sources that are rectangular like TV, phones, etc.)
- **Sky Light** - used to emulate the light from the atmosphere (represents the light that gets scattered in the atmosphere; represents the faint glow of the atmosphere).

**Always select “Build” > “Build Lighting Only” to see changes in light after adding/removing light sources, moving objects in the level, etc.**

If Directional light is static, cannot change lightness, color during the game.
If Directional light is stationary cannot move but can change lightness, color during the game.
If Directional light is movable, it can move and change other properties during the game.

Unreal Engine is the program to run games,
Unreal Editor is the application to create games with Unreal Engine, that play with Unreal Engine.
Play button uses Unreal Engine.

Unreal Editor has several sub-editors under it, for example Level Editor. Level Editor is open from the beginning in the main window.
Other sub-editors are open in a separate window.

**Viewport (in the middle, what we see)** - visual representation of the game, environment, characters, objects and objects not visible in the game (when run)
**Toolbar** - menu for common actions in the Unreal Editor
**Content Browser** - Storing and organising content that you can had to your game: music, meshes, materials, etc. You can create content from Unreal Editor or import content to the Unreal Editor, created elsewhere.
**World Outliner** - List and group objects so they are easy to find; all objects are under one world.
**Details Panel** - when an object is selected, its details show up in this panel. Size, location, material, transform, etc.

Layout is a way to create a custom Layout and you can save it, export it or import it. Not necessary for now.

Editing Mode (Shift + #NUMBER)
Select Editing Mode - used for placing, selecting and manipulating actors

Left button and right button camera moves, while pressing buttons you can also move around your position of the camera with WASD; with Z and C you can zoom and zoom out.

Q and E is to raise and lower camera

You can use command and option keys to move around the object in different ways and axis

Surface Snapping is to make the object not traverse the floor or other objects and snap to surface or object surface.

Types of views for the level:

- Lit:
- Unlit: 
- Wireframe: 3d model in which only the lines and vertices of an object are represented.
- 

Types of perspectives for the level:

- Top: bird’s eyes view
- Bottom:


Viewport Types:
- Default
- Cinema
- 

Show flags is like hiding/showing types of objects or properties in Viewport

G key is to show/unshow game view
CMD+F11 is immersive mode (fullscreen)

Epsilon/Hamburguer menu is the viewport properties:
Field of View (how much of the world/level you see)
Far View Place (it is draw distance; what is drawn to the screen, from how far you are able to see the static meshes)
Screen Percentage (is the screen resolution, lower mean lower quality on the graphics, higher means higher fidelity; it is like resolution in TV: 1080p, 4K, etc.)

When adding content to the project, you need to save in the content browser. If you close the editor and the open project, you will lose the contents of the Content Browser.

**Regarding Mobility property in Transform category from the details panel of an object:**
Most objects in a level/world are static (actor not intended to move or update during gameplay) and are not stationary or movable because the more Movable objects we have, the more processing power is required to use because of the lighting, etc.


**Static mobility:** actor that does not move at all (objects part of the level and background that are no interactive).

**Stationary mobility:** actor that does not move by itself, but can be changed by action from external (for example, objects you can move, bomb from gun, etc.)

**Movable mobility:** actor that moves and state is altered by itself or by another object.
