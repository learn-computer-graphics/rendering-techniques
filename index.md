# Introduction

Explanation and examples of modern rendering techniques commonly used for game engines.

```{tip}
If you are on your phone consider browsing through this <a href="https://rendering-techniques.learn-computer-graphics.com/" target="_blank">link</a> for better performance.
```

## 📖 Sources

### Websites

| Name | Founder(s) | Description |
| --- | --- | --- |
| [WebGL Fundamentals](https://webglfundamentals.org/)         | -                                        | Various tutorial on rendering techniques for WebGL 1 & 2 |
| [Learn OpenGL](https://learnopengl.com/)                     | [Joey de Vries](http://joeydevries.com/) | Various tutorial on rendering techniques for OpenGL      |
| [Vulkan Tutorial](https://vulkan-tutorial.com/) | [Alexander Overvoorde](https://while.io/) | A step-by-step tutorial to use Vulkan |
| [Advances in Real Time rendering](https://advances.realtimerendering.com/) | -                                        | Slides and Videos from SigGraph conferences              |
| [Scratch A Pixel](https://www.scratchapixel.com/)            | -                                        | Tutorial on Computer Graphics theory                     |

### Blogs

| Name | Founder(s) | Description |
| --- | --- | --- |
| [Wicked Engine Dev Blog](https://wickedengine.net/)     | János Turánszki                                              | Dev blog of his game engine         |
| [Our Machinery Dev Blog](https://ourmachinery.com/post) | -                                                            | Dev blog of their game engine       |
| [3D Game engine programming](https://www.3dgep.com/)    | [Robert Grigg](https://www.3dgep.com/author/grigg-rbuas-nl/) | Various articles related to DirectX |
| [The Ryg blog](https://fgiesen.wordpress.com/) | [Fabian Giesen](https://twitter.com/rygorous) | In depth articles about GPU structures. Known for his [Trip trough the graphic pipeline series](https://fgiesen.wordpress.com/2011/07/09/a-trip-through-the-graphics-pipeline-2011-index/) |
| [Adrian Courrèges blog](http://www.adriancourreges.com/blog/) | Adrian Courrèges | Well known for his [Graphics Study](http://www.adriancourreges.com/) series of AAA games. |
| [Alain Gavan blog](https://alain.xyz/blog) | Alain Gavan | Different articles on graphic programming |
| [Humus Name](http://www.humus.name/) | [Emil Persson](https://twitter.com/_humus_?lang=fr) | Blog of a Senior Graphics Engineer at Epic Games |
| [Repi blog](http://repi.blogspot.com/) | [Johan Andersson](https://twitter.com/repi) | Graphics programmer at Dice |
| [Mirror2Mask](https://twitter.com/mirror2mask) | Natalya Tatarchuk | Lead and engineering architect at Bungie |
| [ID software tiago](https://twitter.com/idsoftwaretiago) | [Tiago Sousa](https://www.linkedin.com/in/tsousa/) | Lead rendering programmer at ID Software |
| [PataBlog](https://patapom.com/blog/) | - | Rendering artisan on Dishonored 2 |
| [Create the matrix](reatethematrix.blogspot.com) | [Anoop Ravi Thomas](https://twitter.com/createthematrix) | Senior Graphics Programmer at Rockstar San Diego |
| [Game Art Tricks](https://simonschreibt.de/) | [Simon Schreibt](https://linktr.ee/simonschreibt) | VFX artist at Wild Sheep Studio in Montpellier France |

#### Articles

| Name                                                         | Author            | Description |
| ------------------------------------------------------------ | ----------------- | ----------- |
| [How Unreal renders a frame](https://interplayoflight.wordpress.com/2017/10/25/how-unreal-renders-a-frame/) | Kostas Anagnostou |             |
| [Data driven rendering pipeline](https://jorenjoestar.github.io/post/data_driven_rendering_pipeline/) | Gabriel Sassone   |             |

### Videos

#### Youtube channels

| Name | Author | Description |
| --- | --- | --- |
| [SketchPunkLabs - Learn WebGL](https://www.youtube.com/channel/UCSnyjB_8iVxi2ZAfn_1L6tA) | -      | Various tutorials on rendering techniques with WebGL     |
| [GDC Vault](https://www.gdcvault.com/free)                   | -      | Many conferences from professionals in the game industry |
| [The Cherno](https://www.youtube.com/channel/UCQ-W1KE9EYfdxhL6S4twUNw) | -      | Various videos on programming and graphics programming with content on OpenGL |
| [ChiliTomatoNoodle](https://www.youtube.com/user/ChiliTomatoNoodle) | - | Various videos on programming and graphics programming with content on DirectX |

#### On architecture

| Name                                                         | Description                               | Analysis                                                     |
| ------------------------------------------------------------ | ----------------------------------------- | ------------------------------------------------------------ |
| [GDC - Multithreading Destiny](https://www.youtube.com/watch?v=v2Q_zHG3vqg) | GDC 2015 talk by Barry Genova from Bungie | Destiny datum array accessed with handles, so there is no copy (maybe only on the rendering side, because it is not in sync with the simulation). Check at 29 min<br/><br/>Read and writes are declared with a policy, and a check is done between the jobs to check if the policies are compatible before the task starts.<br/><br/>If it is not, there is an assert and you need to review the way it is structured :<br/>- Start after the end of the overlap (dependency)<br/>- Copy data / cache data<br/>- Queue messages so that the overlapping action is taken latter<br/>- Change algorithm<br/><br/>Those checks are built-out in release. They call it the "Execution Environment" |

### API Code samples

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Sacha Willem's Vulkan](https://github.com/SaschaWillems/Vulkan) | Various rendering techniques with the Vulkan API             |
| [DirectX graphics samples](https://github.com/microsoft/DirectX-Graphics-Samples) | Microsoft official repository for code samples in DirectX 12 |
| [Vulkan Samples](https://github.com/KhronosGroup/Vulkan-Samples) | Khronos official repository for code samples in Vulkan       |

### Renderers

This [Gist](https://gist.github.com/Erfan-Ahmadi/defe4ab99af97f624b68e0dccb0712ea) offers multiple links related to renderers

| Logo | Name | Description |
| --- | --- | --- |
| <img src="https://github.com/DiligentGraphics/DiligentCore/raw/master/media/diligentgraphics-logo.png" height="40px" /> | [Diligent Engine](https://github.com/DiligentGraphics/DiligentEngine) | |
| <img src="https://d2.alternativeto.net/dist/icons/panda3d_144587.png?width=128&height=128&mode=crop&upscale=false" height="40px" /> | [Panda3D](https://www.panda3d.org/) | |
| <img src="https://google.github.io/filament/images/filament_logo_small.png" height="40px" /> | [Google Filament](https://github.com/google/filament) | |
| <img src="https://theforge.dev/wp-content/uploads/2019/09/theforge-marque.svg" height="40px" /> | [The Forge](https://theforge.dev/) | |
| <img src="https://img.itch.zone/aW1hZ2UyL2phbS8zMDg1NzAvNTYyMTEwMi5wbmc=/original/KMlSyG.png" height="40px" /> | [Unity graphics package](https://github.com/Unity-Technologies/Graphics) | |

### Open-source Game engines

| Logo                                                         | Name                                                         | Description |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ----------- |
| <img src="https://cdn.iconscout.com/icon/free/png-256/unreal-engine-555438.png" height="40px" /> | [Unreal Engine 4](https://github.com/EpicGames/UnrealEngine) |             |
| <img src="https://cdn.icon-icons.com/icons2/2248/PNG/512/cryengine_icon_138710.png" height="40px" /> | [Cry Engine](https://github.com/CRYTEK/CRYENGINE)            |             |
| <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Godot_icon.svg/1024px-Godot_icon.svg.png" height="40px" /> | [Godot](https://github.com/godotengine/godot)                |             |
| <img src="https://d2.alternativeto.net/dist/icons/paradox-game-engine_166766.png?width=128&height=128&mode=crop&upscale=false" height="40px" /> | [Stride](https://stride3d.net/)                              |             |
| <img src="https://avatars0.githubusercontent.com/u/6214737?s=200&v=4" height="40px" /> | [NeoAxis Engine](https://github.com/NeoAxis/NeoAxisEngine)   |             |
| <img src="https://avatars2.githubusercontent.com/u/25413467?s=200&v=4" height="40px" /> | [Heaps Haxe engine](https://heaps.io/)                       |             |
| <img src="https://flaxengine.com/wp-content/uploads/2020/12/logo_1_150x100.png" height="40px" /> | [Flax Engine](https://flaxengine.com/)                       |             |
| <img src="https://github.com/turanszkij/WickedEngine/raw/master/Content/logo_small.png" height="40px" /> | [Wicked Engine](https://github.com/turanszkij/WickedEngine)  |             |


### Books

| Name                                                         | Description                                                  | Illustration |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------ |
| [Game Engine Architecture](https://www.gameenginebook.com/)  | A famous book by Jason Gregory, a Naughty Dog engineer       | <img width="80" src="https://www.amazon.fr/images/I/41Hz1rTfm4L._SX260_.jpg">            |
| [Real Time Rendering](http://www.realtimerendering.com/book.html) | Famous book on rendering techniques                          | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/81E9-e9Ek+L.jpg">             |
| [Game Programming Gems Series](http://www.satori.org/game-programming-gems/) | Mark DeLoura compilation of articles by other developers     | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/51fQmX6uduL._SX393_BO1,204,203,200_.jpg">             |
| [GPU Gems Series](https://developer.nvidia.com/gpugems/gpugems/contributors) | Compilation of various articles by developers                | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/51E+10GRNIL.jpg">             |
| [GPU Pro Series](http://gpupro.blogspot.com/)                 | [Wolfgang Engel](http://www.blogger.com/profile/11031097395025597662) compilation of articles by other developers | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/517N2anDNWL._SX384_BO1,204,203,200_.jpg">             |
| [Game Engine Gems Series](http://www.gameenginegems.net/)     | Compilation of articles by developers                        | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/61ojDIZkewL._SX403_BO1,204,203,200_.jpg">             |
| [Fundamentals of Computer Graphics](https://www.oreilly.com/library/view/fundamentals-of-computer/9781482229417/) | A broad book explaining computer graphics from scratch       | <img width="80" src="https://images-na.ssl-images-amazon.com/images/I/51WAZ4sIG3L._SY291_BO1,204,203,200_QL40_ML2_.jpg">             |
| [Physically Based Rendering](http://www.pbr-book.org/)       | Matt Pharr, Wenzel Jakob, and Greg Humphreys revolutionary book on materials | <img width="80" src="https://www.pbrt.org/images/bookcover.png">             |

