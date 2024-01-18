## Visualizing Port Operation 

Port operation simulator.

Due to the increased importance of shipping during the pandemic, the management of ports has
had a significant impact on their costs and efficiency. Therefore, I have developed a simulator
for simulating shipping logistics management to help users simulate processes and improve efficiency.
Below are the features I have implemented:

* Collaborative crane and truck container handling
* Day-night switching using scattered and direct sunlight
* Building a complete port scene

### Architecture
To use the `Visual Studio 2019` environment for rendering objects and scenes, textures, and a Skybox using
`OpenGL`, and to simulate the collaboration between objects to simulate the shipping of cargo in a port 
from the perspective of a gentry.　

### Object Rendering
We use drawEnv to render all objects and scenes, and then separately implement the rendering of `gentry` cranes, `trucks`, `ports`, etc. The following figure is an architectural diagram.
![image](https://github.com/CodeStone1125/NYCU_CG_Fall_2023/assets/72511296/f4c47300-c744-4902-b6a9-f6f7d1741d63)

As for the rendering details, taking the `gentry` crane as an example, the `cabin`, the `body`, the `cabin`, and the `wheel` were designed respectively. These four parts are made using pre-drawn unit cubes and unit cylinders, and then their positions and sizes are altered through push scaling and translation matrices. The following image is an actual shot of the `gentry` crane."
![image](https://github.com/CodeStone1125/NYCU_CG_Fall_2023/assets/72511296/3f5c6740-1315-4856-9de3-b1464036e16e)

### Implement features table
| Render | | |
| --- | --- | --- |
| **Gantry Transporter** | catch/drop | `space` |
|  | up/down | `PageUp/PageDown` |
|  | move | `w/a/s/d` |
| **Truck** | move | `w/a/s/d` |
| **Port** | ***infrastructure*** | |
| **Texture** | ***Above three, skybox*** | |

| Control | | |
| --- | --- | --- |
| **Light** | on/off | `L/I` |
| **Camera** | gantry/truck/free | `1/2/3` |
|  | angle | `mouse` |
