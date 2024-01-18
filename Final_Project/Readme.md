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

| ![image](https://github.com/CodeStone1125/NYCU_CG_Fall_2023/assets/72511296/f4c47300-c744-4902-b6a9-f6f7d1741d63) |
|:-----------------------------------:|
| **Render Overview** |

As for the rendering details, taking the `gentry` crane as an example, the `cabin`, the `body`, the `cabin`, and the `wheel` were designed respectively. These four parts are made using pre-drawn unit cubes and unit cylinders, and then their positions and sizes are altered through push scaling and translation matrices. The following image is an actual shot of the `gentry` crane."

| ![image](https://github.com/CodeStone1125/NYCU_CG_Fall_2023/assets/72511296/3f5c6740-1315-4856-9de3-b1464036e16e) |
|:-----------------------------------:|
| **Gentry** |

### Camera Position
To achieve collaboration in container handling, we implemented the operation of the `gentry`, `truck`, and `third-person` perspectives. These can be switched using the 0/1/2 keys, while the mouse can be used to control the `camera angle`. Below are actual shots of the three perspectives.

| ![image](https://github.com/CodeStone1125/NYCU_CG_Fall_2023/assets/72511296/0403767d-e95b-4c6b-a74e-05fc9d4bbac2) |
|:-----------------------------------:|
| **Camera Position** |

### Lighting and Textures
We rendered textures for all the above-mentioned objects, using fragment shaders and vertex shaders to determine the texture settings. Then, the texture vertices are set to determine the color to be rendered at each point. We also randomly assigned container brands from a pool of 12 different brands, so each time the map is generated, the configuration will be different. For lighting, we implemented `Ambient`, `Diffuse`, `Specular`, `Position`, and `Spot Direction`. The `lights` can be toggled on and off with L/l (lower case) to simulate day and night.

| ![image](https://github.com/CodeStone1125/NYCU_CG_Fall_2023/assets/72511296/5caca5e0-2f7d-49b9-b6a6-7554127f220b) | ![image](https://github.com/CodeStone1125/NYCU_CG_Fall_2023/assets/72511296/a2b4585b-681f-427c-9502-b25f851d9a7c) |
|:-----------------------------------:|:-----------------------------------:|
| **Night(up) vs Day(down)** | **Container** |

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
