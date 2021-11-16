# Unreal Engine

**Actor** - actor used to represent 3D space.

**Brush Actor** - only used for simple geometric shape (used for prototype levels).

**Static Mesh Actor** - 3D object cannot animate, move around the screen, and doesn’t bend or transform by itself; almost every object in a game is a mesh; static mesh has no moving parts; crafted into objects with high-level of detail (used for final project/design). Most static meshes are created in an external 3d modelling program like Maya, 3dstudiomax, blender and then import it to UE editor.

**Skeleton Mesh Actor** - identify individual parts of the skeleton mesh, and how those parts connect and move with one another.

Even if you populate the mesh, it will not move. You need to enable physics in properties of the object.

**Mass Property** - defines weight of object (less means moves more with interaction; more means moves less with interaction).

**Linear/Angular Damping** - amount of drag applied to the movement of the object (less linear means it will not move far, if more linear means it will move very far) _(less angular means it will not rotate a lot or fast, if more angular means it will rotate a lot)_.  -> Resistencia

**Gravity** - property that defines gravity of object (if it has or not)

**Replication Physics to Autonomous Proxy** - used in MP games
