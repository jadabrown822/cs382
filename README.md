Hello World: Your First Program
==================================

## Set up
* __Project Name:__ Hello World
* __Template:__ 3D Core
* __Scene Name:__ (none yet)

### Making a New C# Script
__1.__ Click _Create_ button (+) in Project pane and choose _C# Script_. This add a new script to the Assets folder in the Project pane.

__2.__ Name this script _HellowWorld_ and press Return to set the name.

__3.__ Double-click the name of the icon of the _HelloWorld_ script to launch VS, or C# editor. Line 5, the word after __class__ is __HelloWorld__. If deselect the new C# file in Unity before renaming it, might instead be name __NewBehaviorScript__, which needs to be changed to __HelloWorld__ for the script to work properly.

__4.__ Click mouse on line 10 to place the curosr there, and ehter the code __print("Hello World");__ into line 10 of VS scipt. Make sure to spell and captialize everything correctly and put a semicolon (;) at the end of the line.

```ruby
  // HelloWrold.cs
  
  using System.Collections;
  using System.Collections.Generic;
  using UnityEngine;
  
  public class HelloWorld : MonoBehavior {
    // Start is called before the first frame update
    void Start() {
      print("Hello World");
    }
  
    // Update is called once per frame
    void Update() {}
  }
```

__5.__ Save this scipt by chossing _File > Save_ for the VS menu bar and switch back to Unity (on Windows, _File > Save HelloWorld.cs_).

__6.__ 
* Click and hold the name of the _HelloWorld_ script in the Project pane, drag over the top of the _Main Camera_ in the scene Hierarchy pane, and release the mouse
* A circle with a slash will appear until a GameObject to which script can be attached, and the cursor will change to a box with and arrow (the name doesn't follow the mouse in Windows)
* Asterisks will appear, __need to save the Scene__

__7.__ Save the Scene by choosing _File > Save_ from the main UNity menu. This causes asterisk to disappear. Dragging the Helloworld script into Main Camera _attatches_ the script to Main Camera as a _component_. All objects appear in the scene Hierarchy pane, are known as _GameObjects_, and GameObjects are made up of components.

__8.__ Click _Main Camera_ in the Hierarchy pane, _HelloWorld (Script)_ is listed as one of Main Camera;s components in the inspector pane.

__9.__ Click the _Play_ button (the triangle facing the right at the top of the Unity window).

__10.__ Click the _Play_ buttong in Unity once more ot exit play mode


### Start() versus Update()
__1.__ Go back to VS and edit code

```ruby
  // HelloWrold.cs
  
  using System.Collections;
  using System.Collections.Generic;
  using UnityEngine;
  
  public class HelloWorld : MonoBehavior {
    // Start is called before the first frame update
    void Start() {
      // print("Hello World"); // This line is now ignored
    }
  
    // Update is called once per frame
    void Update() {
      print("Hello World");
    }
  }
```

__2.__ Save the script (replace the original version) and try clicking the _Play_ button again.


### Making Things More Interesting
__1.__ Select Main Camera in the Hierarchy pane.

__2.__ Uncheck the _chekcbox_ to teh left of the name of the _HelloWorld (Script)_ component in the INspector pane (by clicking it)

__3.__ Choose _GameObject > 3D Object > Cube_ from the main Unity menu bar to place a GameObject named _Cube_ in the Scene pane (and in the Hierarchy pane)

__4.__ Click _Cube_ in the Hierarchy pane, and should see it selected with an orange border in the Scene pane.
* __Transform:__ The _Transform_ component sets the position. rotation, and scale of the GameObject.
* __Cube (Mesh Filter):__ The _Mesh Filter_ componet gives the GameObject its three-dimensional shape, which is modeled as a mesh composed of triangles
* __Box Collider:__ _Collider_ compnents enable the GameObject to interact with each other objectd in the phsics simulation that unity runs.
* __Mesh Renderer:__ Whereas the Mesh Filter provides the actual geometry of the GameObject, the _Mesh Renderer_ component makes that geometry visible

__5.__ Look at the transform component in the Inspector, and make sure that the X, Y, and Z Position fileds are all set to 0. To reset the position, rotation, and scale of any Transform by clicking the _three vertical dots_ in the top-right corner of the Transorm component and selecting _Reset_ from the pop-up menu.

__6.__ Add one more component to this GameObject: a _Rigidbody_. With the cube still selected in the Hierarchy, choose _Component > Physics > Rigidbody_ from the menu bar (make sure _Physics > Rigidbody_ and __not__ Physics 2D > Rigidbody 2D), Rigidbody component added to the Inspector
* __Rigidbody:__ The _Rigidbody_ component tells Unity that physics wants to be simulated for this GameObject.

__7.__ Click the _Play_ button, and after a brief pause as Unity gets ready to run, the box falls due to gravity. All the physical simulatoins in Unity are based on the metric system. This means that:
* 1 unit of distance = 1 meter
* 1 unit of mass - 1 kilogram
* The default gravity of -9.8 = 9.8 m/s^2 int the downward (negative y) direction.
* An average human character is about 2 units (2 meters) tall.

__8.__ Click the _Play_ button again to stop the simulation.
