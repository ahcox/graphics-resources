### Graphics Debuggers

#### Renderdoc
[https://github.com/baldurk/renderdoc](https://github.com/baldurk/renderdoc)

* Vulkan, DX11 and OpenGL on Windows
* Vulkan and OpenGL Capture on Linux but no UI so it is better to playback on Windows.

#### apitrace
[http://apitrace.github.io/](http://apitrace.github.io/)

* "trace OpenGL, OpenGL ES, Direct3D, and DirectDraw"
* Android, Linux, OS X, Windows

#### GLAVE
[Wikipedia entry](https://en.wikipedia.org/wiki/GLAVE_(software)).
Vulkan debugger.

#### Others

* <https://github.com/ValveSoftware/vogl>
* <https://github.com/dtrebilco/glintercept>
* <http://benvanik.github.io/WebGL-Inspector/>
* <http://glsl-debugger.github.io/>
* <http://graphics.stanford.edu/~mdfisher/D3D9Interceptor.html>
* <https://msdn.microsoft.com/en-us/library/hh315751.aspx>
* <https://developer.apple.com/library/ios/documentation/3DDrawing/Conceptual/OpenGLES_ProgrammingGuide/ToolsOverview/ToolsOverview.html>
* <http://graphics.stanford.edu/~mdfisher/D3D9Interceptor.html>
* NVIDIA
    * <http://www.nvidia.com/object/nsight.html>
    * <https://developer.nvidia.com/linux-graphics-debugger>
    * <https://developer.nvidia.com/tegra-graphics-debugger>
* AMD
    * <http://developer.amd.com/tools-and-sdks/opencl-zone/codexl/>
    * <http://developer.amd.com/tools-and-sdks/graphics-development/gpu-perfstudio/>
* Intel: <https://software.intel.com/en-us/gpa>
* Mobile:
    * ARM Mali: <http://malideveloper.arm.com/resources/tools/mali-graphics-debugger/>
    * PowerVR: <http://community.imgtec.com/developers/powervr/tools/pvrtrace/>
    * Qualcomm Adreno GPU Profiler: <https://developer.qualcomm.com/software/adreno-gpu-profiler>

### Realtime Rendering

*  [A deferred material rendering system by Tomasz Stachowiak](https://onedrive.live.com/view.aspx?resid=EBE7DEDA70D06DA0!115&app=PowerPoint&authkey=!AP-pDh4IMUug6vs)
 
#### Realtime Physically Based Rendering [PBR]

* [A Glossary of Physically-Based Reflectance](http://web.archive.org/web/20180218190946/http://jankautz.com/courses/GameCourse/08_Glossary.pdf)
* [Siggraph 2006 Course: Physically-Based Reflectance for Games](http://web.archive.org/web/20161027153222/http://jankautz.com/courses/GameCourse/)
    * [Reflectance](http://web.archive.org/web/20170403181313/http://jankautz.com/courses/GameCourse/02_Reflectance.pdf)

##### Panda3D RenderPipeline

* [http://www.panda3d.org/forums/viewtopic.php?f=6&t=17050](http://www.panda3d.org/forums/viewtopic.php?f=6&t=17050)
* [https://github.com/tobspr/RenderPipeline](http://www.panda3d.org/forums/viewtopic.php?f=6&t=17050)


#### Realtime Shadows

Realtime shadows have traditionaly come down to one of three options.

1. **Projected Shadows**: Real or proxy geometry such as a disk projected onto a shadow-receiving surface, most simply a ground plane.
1. **Shadow Volumes**: Extruding silhouette edges of shadow casting objects from the point of view of a light source.
                           Drawing them into stencil buffer of main camera viewpoint to count whether nearest visible surfaces are in shadow or not. 
1. **Shadow Maps**: Draw scene into a texture map from point of view of a light to amortize calculation of visibility of all locations in the scene
                        from the light.
                        During shading points in the scene from main viewpoint, project into the shadow texture map to find out whether they are
                        directly lit from a particular light.

* [Siggraph 2004 Shadows Course](http://web.archive.org/web/20161027151834/http://jankautz.com/courses/ShadowCourse/)
    * [Shadow Mapping](http://web.archive.org/web/20170403184159/http://jankautz.com/courses/ShadowCourse/02-ShadowMaps.pdf)
    * [Perspective Shadow Maps](http://web.archive.org/web/20170403124905/http://jankautz.com/courses/ShadowCourse/03-PerspectiveSM.pdf)
    * [Shadow Silhouette Maps](http://web.archive.org/web/20170403181420/http://jankautz.com/courses/ShadowCourse/04-SilhouetteMap.pdf)
    * [Soft Shadow Maps Soft Shadow Maps
for Linear Lights](http://web.archive.org/web/20170403134344/http://jankautz.com/courses/ShadowCourse/05-LinearLights.pdf)
    * [Rendering Fake Soft Shadows
with Smoothies](http://web.archive.org/web/20170403181149/http://jankautz.com/courses/ShadowCourse/06-Smoothies.pdf)
    * [Practical and Robust Stenciled Shadow Volumes for
Hardware-Accelerated Rendering ](http://web.archive.org/web/20180218185437/http://jankautz.com/courses/ShadowCourse/07-ShadowVolumes.pdf)
    * [A Soft Shadow Volume Algorithm](http://web.archive.org/web/20170403134902/http://jankautz.com/courses/ShadowCourse/08-SoftShadowVolumes.pdf)





Link [here](http://ahcox.com/graphics/graphics-resources). [Edit](https://github.com/ahcox/graphics-resources/edit/master/README.md) this page.
