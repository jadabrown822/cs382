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
  
  public class HelloWorld : MonoBehaviour {
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
  
  public class HelloWorld : MonoBehaviour {
    // Start is called before the first frame update
    void Start() {
      // print("Hello World");  This line is now ignored
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


### Making a Prefab
A prefab is a reusable element in a project that can be instantiated (cloned into existance) any number of times

* A prefab named _Cube_ had been created inthe Project pane. Indication by tge blue cube iton next to it.
* The name of the Cube GameObject in the hierarchy has turned blue. If the GameObject has a blue name in the hierarchy it means that the GameObject is an instance of a prefab (which is like a copy make from the prefab mold).

Just for the sake of clarity, rename the Cube Prefab int eh Project pane to _Cube Prefab_

__1.__ Click once on the _Cube_ prefab in the Project pane to select it. Then click a second time to rename it(can press F2 after it's selected to rename it) and then change the name to _Cube Prefab_.

__2.__ Now that prefab is set up, the instance of the cube in the scene is not needed any more. Click _Cube_ in the Hierarchy pane (not the Project Pane!). Choose _Edit > Delete_ from the menu bar; the cube disappears from teh scene.

__3.__ Save the Scene by choosing _File > Save_ from the Unity menu.

__4.__ Choose _Assets > Create > C# Script_ from the main menu bar and rename the newly created script _CubeSpawner_.

__5.__ Double-click the _CubeSpawner_ script to open VS

```ruby
  using System.Collections;
  using System.Collectoins.Generic;
  Using UnityEngine;
  
  public class CubeSpawner : MonoBehaviour {
    public GameObject cubePrefabVar;
  
    // Start is called before the first frame update
    void Start() {
      Instantiate (cubePreFabVar);
    }
    
    // Update is capped once per frame
    void Update() {}
  
  }
```

__6.__ Save the CubeSpawner script in VS (_File > Save_) and return to unity.

__7.__ In Unity, drag the _CubeSpawner_ script over to _Main Camera_

__8.__ Click _Main Camera_ in the Hierarchy pane.

__9.__ In the Inspactor, __cubePreFabVar__ currently has no value assigned. Click the circular target to the right of the cubePrefab variabel value to open the _Select GameObject_ dialog box from can select a prefab to assign to this variable
* __Make sure that the _Assets_ tab is selected.__ (The Assets tab shows GameObject in Project pane, where as the SCene tab shows GameObjects in the Hierarchy.)
* __Double-click Cube Prefab to select it__

__10.__ In the inspector that the value of __cubePreFabCar__ is _Cube Prefab_ (and choosing it from the Assets tab ensured it was one in the Project pane). To double-check this, click the value _Cube Prefab_ in the Inspector, and _Cube Prefab_ is highlighted in yellow in the Project pane.

__11.__ Click the _Play_ button. A single _Cube Prefab(Clone)_ GameObject is instantiated in the Hierarchy. The __Start()__ function is called once, and it creates a single instance (or clone) of the Cube Prefab.

__12.__ Switch to VS and edit the code:
* Comment out the __Instantiate(cubePreFabVar)__ call on line 12 in the __Start()__ function.
* Add an __Instantiate(cubePreFabVar);__ statement to line 18 in the __Update()__ function

```ruby
  using System.Collections;
  using System.Collectoins.Generic;
  Using UnityEngine;
  
  public class CubeSpawner : MonoBehaviour {
    public GameObject cubePrefabVar;
  
    // Use this for initialization
    void Start() {
      // Instantiate (cubePreFabVar);
    }
    
    // Update is capped once per frame
    void Update() {
      Instantiate (cubePreFabVar);
    }
  
  }
```

__13.__ Save the CubeSpawner script, and switch back to Unity

__14.__ Save Scene, and then click _Play_
