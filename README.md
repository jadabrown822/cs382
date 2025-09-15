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
* Click and hold the name of the _HelloWorld_script in the Project pane, drag over the top of the _Main Camera_ in the scene Hierarchy pane, and release the mouse
* A circle with a slash will appear until a GameObject to which script can be attached, and the cursor will change to a box with and arrow (the name doesn't folloe the mouse in Windows)
* Asterisks will appear, __need to save the Scene__
