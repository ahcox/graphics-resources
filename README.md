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

### Real-Time Rendering

*  [A deferred material rendering system by Tomasz Stachowiak](https://onedrive.live.com/view.aspx?resid=EBE7DEDA70D06DA0!115&app=PowerPoint&authkey=!AP-pDh4IMUug6vs)
 
#### Real-Time Physically Based Rendering [PBR]

* [A Glossary of Physically-Based Reflectance](http://web.archive.org/web/20180218190946/http://jankautz.com/courses/GameCourse/08_Glossary.pdf)
* [Siggraph 2006 Course: Physically-Based Reflectance for Games](http://web.archive.org/web/20161027153222/http://jankautz.com/courses/GameCourse/)
    * [Reflectance](http://web.archive.org/web/20170403181313/http://jankautz.com/courses/GameCourse/02_Reflectance.pdf)

##### Panda3D RenderPipeline

* [http://www.panda3d.org/forums/viewtopic.php?f=6&t=17050](http://www.panda3d.org/forums/viewtopic.php?f=6&t=17050)
* [https://github.com/tobspr/RenderPipeline](http://www.panda3d.org/forums/viewtopic.php?f=6&t=17050)


#### Real-Time Shadows

Real-time shadows have traditionaly come down to [one of three options](http://web.archive.org/web/20170909015242/http://www.vectorstorm.org/2012/05/15/lets-talk-about-shadows/).

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

* [Convolution Shadow Maps](http://web.archive.org/web/20161027151805/http://jankautz.com/publications/csmEGSR07.pdf)
  _"**Abstract**:
  We present Convolution Shadow Maps, a novel shadow representation that affords efficient arbitrary linear filtering
  of shadows. Traditional shadow mapping is inherently non-linear w.r.t. the stored depth values, due to the
  binary shadow test. We linearize the problem by approximating shadow test as a weighted summation of basis
  terms. We demonstrate the usefulness of this representation, and show that hardware-accelerated anti-aliasing
  techniques, such as tri-linear filtering, can be applied naturally to Convolution Shadow Maps. Our approach can
  be implemented very efficiently in current generation graphics hardware, and offers real-time frame rates."_

* [Exponential Shadow Maps](http://web.archive.org/web/20161027150516/http://jankautz.com/publications/esm_gi08.pdf)
  _"**Abstract**:
   Rendering high-quality shadows in real-time is a challenging problem.
   Shadow mapping has proved to be an efficient solution, as it
   scales well for complex scenes. However, it suffers from aliasing
   problems. Filtering the shadow map alleviates aliasing, but unfortunately,
   native hardware-accelerated filtering cannot be applied, as
   the shadow test has to take place beforehand.
   We introduce a simple approach to shadow map filtering, by approximating
   the shadow test using an exponential function. This
   enables us to pre-filter the shadow map, which in turn allows for
   high quality hardware-accelerated filtering. Compared to previous
   filtering techniques, our technique is faster, consumes less memory
   and produces less artifacts"_
* [Variance Soft Shadow Mapping](http://web.archive.org/web/20161027145838/http://jankautz.com/publications/VSSM_PG2010.pdf)
  _"**Abstract**
   We present variance soft shadow mapping (VSSM) for rendering plausible soft shadow in real-time. VSSM is based
   on the theoretical framework of percentage-closer soft shadows (PCSS) and exploits recent advances in variance
   shadow mapping (VSM). Our new formulation allows for the efficient computation of (average) blocker distances,
   a common bottleneck in PCSS-based methods. Furthermore, we avoid incorrectly lit pixels commonly encountered
   in VSM-based methods by appropriately subdividing the filter kernel. We demonstrate that VSSM renders highquality
   soft shadows efficiently (usually over 100 fps) for complex scene settings. Its speed is at least one order of
   magnitude faster than PCSS for large penumbra."_
   
   
* [SIGGRAPH 2013, Playing with Real-Time Shadows, Nikolas Kasyan](http://web.archive.org/web/20161027041400/http://www.crytek.com/download/Playing%20with%20Real-Time%20Shadows.pdf)
   Covers the composition of an overall shadowing approach for an AAA game from a number of techniques:
   Deferred Shadows,
   Cascaded shadow maps,
   Soft Shadows Approximation,
   Shadows & Transparency,
   Contact Shadows/SSDO,
   Screen Space Self-Shadowing,
   Volumetric shadows,
   Area Light Shadows.
   
##### Variance Shadow Mapping
* [Original paper with source](http://web.archive.org/web/20180102152226/http://www.punkuser.net/vsm/)
* [GDC 2006 Presentation](http://web.archive.org/web/20060501230037/http://download.nvidia.com:80/developer/presentations/2006/gdc/2006-GDC-Variance-Shadow-Maps.pdf)
* [Nvidia 2007 Implementation](http://web.archive.org/web/20120121060035/http://developer.download.nvidia.com/SDK/10.5/direct3d/Source/VarianceShadowMapping/Doc/VarianceShadowMapping.pdf)
* [Links](http://lousodrome.net/blog/light/2012/01/23/variance-shadow-maps/)


Link [here](http://ahcox.com/graphics/graphics-resources). [Edit](https://github.com/ahcox/graphics-resources/edit/master/README.md) this page.
