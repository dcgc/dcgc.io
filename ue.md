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

Intensity of the light changes the intensity (amount/brightness) of the light.
Color Picket gives the color for the light.
Source Angle and Source Soft Angle determines how soft the edges of the light will be. This is to create the effect of hard and soft shadows when casting light into an object and/or scene. The higher the volume, the softer the lights. On top of both properties, you can put Ray Tracing functionality for reflective lighting properties.

Temperature (enable/tick the box): it changes the color of the light (warm/cold light).

Affects the World is an option to enable/disable the light (effect in the level).

Cast Shadows is an option to disable/enable shadows created from the light (can be used for performance saving). A lot of objects have the same property (property of material of objects).

Indirect Lighting Intensity: reflected lights that can light an object in a level.

Volumetric Scattering Intensity - it is lighting related with fog.

Pointlight/Spotlight Properties:
Radius:
  Attenuation Radius: Sets the reach of the light and defines what objects it will affect; serves as the outer bounds when calculating the falloff of the light.
  Source Radius: simulates the size of the light source.
  Soft Source Radius: you can set how full/gradient your light is (inside of what you set for source radius).
  Source Length: gives elongated or tube-like reflective shape, as if the light were coming form a fluorescent light fixture.

Spotlight Properties:
Light cones: 
  Spotlight emits light from a single point in a cone shape. Users are given two cones to shape the light - the Inner Cone Angle and Outer Cone Angle.
  Set the outer cone angle greater than the inner cone angle to create a soft-edged spotlight. Set the inner cone agle greater than the outer to create a hard-edged spotlight. 
  With inner light, you set the strong/real light size. With outer light, you set the dimmer light / fallout portion light size.
  This effect is done on real spotlights with the barn doors (visors/flaps) on the sides of the light.
  
Rectlight/Spotlight Properties:
  Source Width/Height: size of light.
  Barn Door Angle: the angle of the visors on the spotlight/rectlight.
  Barn Door Lenght: the size of the visors on the spotlight/rectlight.
  Source texture: it is to cast the light with a filter (texture).

DirectionalLight Properties:
  Atmosphere and Cloud Section:
    Atmosphere Sun Light: the AtmosphereFog actor will use rotation of DirectionalLight actor to determine where the Sun disk should be placed in the sky. 
    Cast Shadows on Cloud: cast any shadows from opaque meshes onto clouds.
    Cast Shadows on Atmosphere: cast any shadows from opaque meshes into the atmosphere when a SkyAtmosphere is used.
    Cast Cloud Shadows: cast any shadows from the clouds onto the atmosphere and other scene elements.
    Cloud Scattered Luminance Scale : color of the clouds.
    CTRL+L with mouse, is a shortcut for rotating the Sun in any axis.
    
SkyLight Properties:

    
AtmosphericFog Actor (old way): provide a realistic sense of atmosphere, air density, and light scattering through atmospheric media.
  
BP_SkySphere Actor (old way): physically-based sky and atmosphere-rendering technique, provides clouds to the level.

Sky Atmosphere Actor (new way, for both previous actors): can more acuratelly render how a sky should look like at different times of a day (Sun position). Allows for smoother transition from ground to atmosphere (outer space).
  Sky Atmosphere Properties:
    {Atmosphere} Multiscattering: defines how much of the sun light scatters or reflects/bounces on the atmosphere (maximum is 1.0).
    {Planet} Transform Mode: used to define where the bounds of the Planet should exist based on the location/position of the Sky Atmosphere Actor.
        Planet Top at Absolute World Position: puts the ground level (surface of the Planet) of atmosphere at world origin coordinates (0,0,0) in the scene. Sky Atmosphere is not movable when this option is selected. 
        Planet Top at Component Transform: puts ground level (surface of the Planet) of atmosphere relative to component's transform origin. Moving Sky Atmosphere, moves atmosphere within the level. Actor
        Planet Center at Component Transform: puts atmosphere centered to the component's transform origin. Moving Sky Atmosphere, moves atmosphere within the level.
    {Planet} Ground Albedo: determines the color of the light that is reflected.
    {Atmosphere Rayleigh} Rayleigh Scattering: determines the densedity of the scattering of the "color" of sky depending on Sun position or time of day, due to smaller particles. Example, sky appears red or more yellow/orange at sunset due to the Sun casting light to less of the sky and therefore less particles (less dense air), giving this effect. When the Sun is high in the sky, the sky is bluer or blue and we sees less of the red (more dense air) because of more particles in the sky.
    {Atmosphere Rayleigh} Rayleigh Exponential Distribute: how high up you have to go in order for the air to get less dense.
    {Atmosphere Mie} Mie Scattering: involves light scattering due larger particles such as dust or air pollution. Example, use this effect to create a haze or dust effect from a desert, or to create a regular fog.
    {Atmosphere Absorption} Absorption Scale: set how much light gets absorved in the atmosphere.
    
VolumetricCloud actor: you can customize the appearence of the clouds. More realistic clouds.
    Layer Bottom Altitude: specifies distance from the ground in Km, for the clouds.
    Layer Height: specifies distance from the ground in Km, for the clouds to stop appearing.
  
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


**PlayerStart Actor:** defines where the player will start the level.
  BadSize icon on PlayerStart will say that the starting position for the player is not valid (e.g., clipping on floor).


**Component** is a group of actors combined together. You start by adding an actor to the level, and then, on the properties, with the add button, you select another actor to be added as a component. For example, static mesh of cylinder and then component of spotlight on one of the ends of the cylinder, to make a flashlight. When the actor is rotated or moved in an axis, all the components are also rotated and/or moved based on the root of the center of the actor.


**Movement Actor:** adds movement to a object.
  {Rotating Component} Rotation Rate: the speed at which it rotates.
  {Rotating Component} Pivot Translation: distance of rotation within the center, if it rotates itself, rotates around, etc.
  
Volumes: 
