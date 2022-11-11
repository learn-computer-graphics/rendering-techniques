# Introduction

Explanation and examples of modern rendering techniques commonly used for game engines.

```{tip}
If you are on your phone consider browsing through this <a href="https://rendering-techniques.learn-computer-graphics.com/" target="_blank">link</a> for better performance.
```

## About

This website will show and explain multiple usages of the low-level rendering library  <a href='https://github.com/ConfettiFX/The-Forge' target='_blank'>The Forge</a>. It works in conjunction with the repository  <a href='https://github.com/learn-computer-graphics/the-forge-samples' target='_blank'>the-forge-samples</a> which implements said tutorials.

## 📖 Sources

### Websites

| Name | Founder(s) | Description |
| --- | --- | --- |
|  <a href='https://webglfundamentals.org/' target='_blank'>WebGL Fundamentals</a>         | -                                        | Various tutorial on rendering techniques for WebGL 1 & 2 |
|  <a href='https://learnopengl.com/' target='_blank'>Learn OpenGL</a>                     |  <a href='http://joeydevries.com/' target='_blank'>Joey de Vries</a> | Various tutorial on rendering techniques for OpenGL      |
|  <a href='https://vulkan-tutorial.com/' target='_blank'>Vulkan Tutorial</a> |  <a href='https://while.io/' target='_blank'>Alexander Overvoorde</a> | A step-by-step tutorial to use Vulkan |
|  <a href='https://advances.realtimerendering.com/' target='_blank'>Advances in Real Time rendering</a> | -                                        | Slides and Videos from SigGraph conferences              |
|  <a href='https://www.scratchapixel.com/' target='_blank'>Scratch A Pixel</a>            | -                                        | Tutorial on Computer Graphics theory                     |

### Blogs

| Name | Founder(s) | Description |
| --- | --- | --- |
|  <a href='https://wickedengine.net/' target='_blank'>Wicked Engine Dev Blog</a>     | János Turánszki                                              | Dev blog of his game engine         |
|  <a href='https://ourmachinery.com/post' target='_blank'>Our Machinery Dev Blog</a> | -                                                            | Dev blog of their game engine       |
|  <a href='https://www.3dgep.com/' target='_blank'>3D Game engine programming</a>    |  <a href='https://www.3dgep.com/author/grigg-rbuas-nl/' target='_blank'>Robert Grigg</a> | Various articles related to DirectX |
|  <a href='https://fgiesen.wordpress.com/' target='_blank'>The Ryg blog</a> |  <a href='https://twitter.com/rygorous' target='_blank'>Fabian Giesen</a> | In depth articles about GPU structures. Known for his  <a href='https://fgiesen.wordpress.com/2011/07/09/a-trip-through-the-graphics-pipeline-2011-index/' target='_blank'>Trip trough the graphic pipeline series</a> |
|  <a href='http://www.adriancourreges.com/blog/' target='_blank'>Adrian Courrèges blog</a> | Adrian Courrèges | Well known for his  <a href='http://www.adriancourreges.com/' target='_blank'>Graphics Study</a> series of AAA games. |
|  <a href='https://alain.xyz/blog' target='_blank'>Alain Gavan blog</a> | Alain Gavan | Different articles on graphic programming |
|  <a href='http://www.humus.name/' target='_blank'>Humus Name</a> |  <a href='https://twitter.com/_humus_?lang=fr' target='_blank'>Emil Persson</a> | Blog of a Senior Graphics Engineer at Epic Games |
|  <a href='http://repi.blogspot.com/' target='_blank'>Repi blog</a> |  <a href='https://twitter.com/repi' target='_blank'>Johan Andersson</a> | Graphics programmer at Dice |
|  <a href='https://twitter.com/mirror2mask' target='_blank'>Mirror2Mask</a> | Natalya Tatarchuk | Lead and engineering architect at Bungie |
|  <a href='https://twitter.com/idsoftwaretiago' target='_blank'>ID software tiago</a> |  <a href='https://www.linkedin.com/in/tsousa/' target='_blank'>Tiago Sousa</a> | Lead rendering programmer at ID Software |
|  <a href='https://patapom.com/blog/' target='_blank'>PataBlog</a> | - | Rendering artisan on Dishonored 2 |
|  <a href='reatethematrix.blogspot.com' target='_blank'>Create the matrix</a> |  <a href='https://twitter.com/createthematrix' target='_blank'>Anoop Ravi Thomas</a> | Senior Graphics Programmer at Rockstar San Diego |
|  <a href='https://simonschreibt.de/' target='_blank'>Game Art Tricks</a> |  <a href='https://linktr.ee/simonschreibt' target='_blank'>Simon Schreibt</a> | VFX artist at Wild Sheep Studio in Montpellier France |

#### Articles

| Name                                                         | Author            | Description |
| ------------------------------------------------------------ | ----------------- | ----------- |
|  <a href='https://interplayoflight.wordpress.com/2017/10/25/how-unreal-renders-a-frame/' target='_blank'>How Unreal renders a frame</a> | Kostas Anagnostou |             |
|  <a href='https://jorenjoestar.github.io/post/data_driven_rendering_pipeline/' target='_blank'>Data driven rendering pipeline</a> | Gabriel Sassone   |             |

### Videos

#### Youtube channels

| Name | Author | Description |
| --- | --- | --- |
|  <a href='https://www.youtube.com/channel/UCSnyjB_8iVxi2ZAfn_1L6tA' target='_blank'>SketchPunkLabs - Learn WebGL</a> | -      | Various tutorials on rendering techniques with WebGL     |
|  <a href='https://www.gdcvault.com/free' target='_blank'>GDC Vault</a>                   | -      | Many conferences from professionals in the game industry |
|  <a href='https://www.youtube.com/channel/UCQ-W1KE9EYfdxhL6S4twUNw' target='_blank'>The Cherno</a> | -      | Various videos on programming and graphics programming with content on OpenGL |
|  <a href='https://www.youtube.com/user/ChiliTomatoNoodle' target='_blank'>ChiliTomatoNoodle</a> | - | Various videos on programming and graphics programming with content on DirectX |

#### On architecture

| Name                                                         | Description                               | Analysis                                                     |
| ------------------------------------------------------------ | ----------------------------------------- | ------------------------------------------------------------ |
|  <a href='https://www.youtube.com/watch?v=v2Q_zHG3vqg' target='_blank'>GDC - Multithreading Destiny</a> | GDC 2015 talk by Barry Genova from Bungie | Destiny datum array accessed with handles, so there is no copy (maybe only on the rendering side, because it is not in sync with the simulation). Check at 29 min<br/><br/>Read and writes are declared with a policy, and a check is done between the jobs to check if the policies are compatible before the task starts.<br/><br/>If it is not, there is an assert and you need to review the way it is structured :<br/>- Start after the end of the overlap (dependency)<br/>- Copy data / cache data<br/>- Queue messages so that the overlapping action is taken latter<br/>- Change algorithm<br/><br/>Those checks are built-out in release. They call it the "Execution Environment" |

### API Code samples

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|  <a href='https://github.com/SaschaWillems/Vulkan' target='_blank'>Sacha Willem's Vulkan</a> | Various rendering techniques with the Vulkan API             |
|  <a href='https://github.com/microsoft/DirectX-Graphics-Samples' target='_blank'>DirectX graphics samples</a> | Microsoft official repository for code samples in DirectX 12 |
|  <a href='https://github.com/KhronosGroup/Vulkan-Samples' target='_blank'>Vulkan Samples</a> | Khronos official repository for code samples in Vulkan       |

### Renderers

This  <a href='https://gist.github.com/Erfan-Ahmadi/defe4ab99af97f624b68e0dccb0712ea' target='_blank'>Gist</a> offers multiple links related to renderers

| Logo | Name | Description |
| --- | --- | --- |
| <img src="https://github.com/DiligentGraphics/DiligentCore/raw/master/media/diligentgraphics-logo.png" height="40px" /> |  <a href='https://github.com/DiligentGraphics/DiligentEngine' target='_blank'>Diligent Engine</a> | |
| <img src="https://d2.alternativeto.net/dist/icons/panda3d_144587.png?width=128&height=128&mode=crop&upscale=false" height="40px" /> |  <a href='https://www.panda3d.org/' target='_blank'>Panda3D</a> | |
| <img src="https://google.github.io/filament/images/filament_logo_small.png" height="40px" /> |  <a href='https://github.com/google/filament' target='_blank'>Google Filament</a> | |
| <img src="https://theforge.dev/wp-content/uploads/2019/09/theforge-marque.svg" height="40px" /> |  <a href='https://theforge.dev/' target='_blank'>The Forge</a> | |
| <img src="https://img.itch.zone/aW1hZ2UyL2phbS8zMDg1NzAvNTYyMTEwMi5wbmc=/original/KMlSyG.png" height="40px" /> |  <a href='https://github.com/Unity-Technologies/Graphics' target='_blank'>Unity graphics package</a> | |

### Open-source Game engines

| Logo                                                         | Name                                                         | Description |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ----------- |
| <img src="https://cdn.iconscout.com/icon/free/png-256/unreal-engine-555438.png" height="40px" /> |  <a href='https://github.com/EpicGames/UnrealEngine' target='_blank'>Unreal Engine 4</a> |             |
| <img src="https://cdn.icon-icons.com/icons2/2248/PNG/512/cryengine_icon_138710.png" height="40px" /> |  <a href='https://github.com/CRYTEK/CRYENGINE' target='_blank'>Cry Engine</a>            |             |
| <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Godot_icon.svg/1024px-Godot_icon.svg.png" height="40px" /> |  <a href='https://github.com/godotengine/godot' target='_blank'>Godot</a>                |             |
| <img src="https://d2.alternativeto.net/dist/icons/paradox-game-engine_166766.png?width=128&height=128&mode=crop&upscale=false" height="40px" /> |  <a href='https://stride3d.net/' target='_blank'>Stride</a>                              |             |
| <img src="https://avatars0.githubusercontent.com/u/6214737?s=200&v=4" height="40px" /> |  <a href='https://github.com/NeoAxis/NeoAxisEngine' target='_blank'>NeoAxis Engine</a>   |             |
| <img src="https://avatars2.githubusercontent.com/u/25413467?s=200&v=4" height="40px" /> |  <a href='https://heaps.io/' target='_blank'>Heaps Haxe engine</a>                       |             |
| <img src="https://flaxengine.com/wp-content/uploads/2020/12/logo_1_150x100.png" height="40px" /> |  <a href='https://flaxengine.com/' target='_blank'>Flax Engine</a>                       |             |
| <img src="https://github.com/turanszkij/WickedEngine/raw/master/Content/logo_small.png" height="40px" /> |  <a href='https://github.com/turanszkij/WickedEngine' target='_blank'>Wicked Engine</a>  |             |


### Books

| Name                                                         | Description                                                  | Illustration |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------ |
|  <a href='https://www.gameenginebook.com/' target='_blank'>Game Engine Architecture</a>  | A famous book by Jason Gregory, a Naughty Dog engineer       | <img width="80" src="https://www.amazon.fr/images/I/41Hz1rTfm4L._SX260_.jpg">            |
|  <a href='http://www.realtimerendering.com/book.html' target='_blank'>Real Time Rendering</a> | Famous book on rendering techniques                          | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/81E9-e9Ek+L.jpg">             |
|  <a href='http://www.satori.org/game-programming-gems/' target='_blank'>Game Programming Gems Series</a> | Mark DeLoura compilation of articles by other developers     | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/51fQmX6uduL._SX393_BO1,204,203,200_.jpg">             |
|  <a href='https://developer.nvidia.com/gpugems/gpugems/contributors' target='_blank'>GPU Gems Series</a> | Compilation of various articles by developers                | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/51E+10GRNIL.jpg">             |
|  <a href='http://gpupro.blogspot.com/' target='_blank'>GPU Pro Series</a>                 |  <a href='http://www.blogger.com/profile/11031097395025597662' target='_blank'>Wolfgang Engel</a> compilation of articles by other developers | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/517N2anDNWL._SX384_BO1,204,203,200_.jpg">             |
|  <a href='http://www.gameenginegems.net/' target='_blank'>Game Engine Gems Series</a>     | Compilation of articles by developers                        | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/61ojDIZkewL._SX403_BO1,204,203,200_.jpg">             |
|  <a href='https://www.oreilly.com/library/view/fundamentals-of-computer/9781482229417/' target='_blank'>Fundamentals of Computer Graphics</a> | A broad book explaining computer graphics from scratch       | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/51WAZ4sIG3L._SY291_BO1,204,203,200_QL40_ML2_.jpg">             |
|  <a href='http://www.pbr-book.org/' target='_blank'>Physically Based Rendering</a>       | Matt Pharr, Wenzel Jakob, and Greg Humphreys revolutionary book on materials | <img width="80" src="https://www.pbrt.org/images/bookcover.png">             |

