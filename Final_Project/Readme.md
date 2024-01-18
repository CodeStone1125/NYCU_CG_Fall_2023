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
