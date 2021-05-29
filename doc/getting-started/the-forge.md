# The Forge

<img src="https://github.com/ConfettiFX/The-Forge/raw/master/Screenshots/The%20Forge%20-%20Colour%20Black%20Landscape.png" width="150px" />

## What is The Forge ?

[The Forge](https://github.com/ConfettiFX/The-Forge) is a cross-platform rendering framework developed by [ConfettiFX](https://theforge.dev/). It's role is to [ease the developer's burden](https://github.com/ConfettiFX/The-Forge/issues/99) when it comes to render things on screen. It is a low-level abstraction layer for the modern Graphic APIs such as [DirectX12](https://en.wikipedia.org/wiki/DirectX) and [Vulkan](https://en.wikipedia.org/wiki/Vulkan_(API)). For accredited developers, it can also support all major game consoles (Xbox, Playstation 5, Switch, etc). With The Forge, write once, run (almost) everywhere. 

Compared to an in-house project, using this library is the guarantee to have a more stable solution, field tested and with a clear and concise API validated by veteran of the industry.  The first official release was done in 2018, so it's fair to say that the codebase is quite recent. In the few years of development that followed, the maintainers at ConfettiFX added multiple features in the engine related to the work they do as consultants for external game studios.

### Some engine features

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Custom Entity Component System ([ECS](https://github.com/guillaume-haerinck/met-ecs)) | The [ECS](https://docs.unity3d.com/Packages/com.unity.entities@0.16/manual/index.html) programming pattern is a quite recent paradigm which provide a code structure better suited for performance and parallelism. They developed an in-house ECS which can be integrated easily in the rendering engine. |
| Cross-platform file system                                   | The inclusion of a platform-agnostic standard library to handle filesystem in C++ is recent (v17), so they provide a C-like API which is guarantee to work on any platforms The Forge runs on. |
| [Micro profiler](https://github.com/ConfettiFX/The-Forge/wiki/Microprofiler---How-to-Use) | One of the main goal of a library like The Forge is performance, so it is crucial to be able to monitor it easily and this is exactly what this tool is for. |
| [Global shading language](https://github.com/ConfettiFX/The-Forge/wiki/The-Forge-Shading-Language-(FSL)) | Multiple APIs uses multiple shading languages. With TheForge it is possible to write every shader with a superset of HLSL called FSL, and a translator will take care of translating the FSL to the API in use. |
| Multi-threaded rendering                                     | One of the goal of the new Graphic API, besides being closer to the metal, is to be suited for multi-threading environments. TheForge keeps this particularity and handle multi-threaded command buffer generation as well as async and multi-threaded resource loading. |
| [Input handling](https://github.com/ConfettiFX/The-Forge/wiki/Input-System-Overview) | They provide an input-handling API similar to what is available in Unity in C#. |
| LUA Scripting                                                | It is possible to use basic scripting to animate objects, lights and cameras. |

### Some visual features

ConfettiFX also has closed-source technologies that you can see them [here](https://theforge.dev/products/). What's below is available freely in TheForge.

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Custom debug UI                                              | They provide a custom ui system based on [ImGui](https://github.com/ocornut/imgui). |
| Skinning animation system                                    | It is based on based on the library [OZZ](https://github.com/guillaumeblanc/ozz-animation) and also support invert kinematic and joints. |
| Sparse Virtual Textures                                      | The Forge is able to use very large textures, the idea is that only the visible portion is loaded on the GPU. |
| [TressFX](https://www.amd.com/fr/technologies/tressfx) by AMD | A real-time hair rendering system that they helped developed. It was used for the [Tomb Raider](https://en.wikipedia.org/wiki/Tomb_Raider_(2013_video_game)) game in 2013 |
| Multiple shadow map generation systems                       | They support [exponential shadow map](https://pixelstoomany.wordpress.com/category/shadows/exponential-shadow-maps/), [adaptive shadow map with parallax correction cache](http://gpuzen.blogspot.com/2019/05/gpu-zen-2-parallax-corrected-cached.html) and [signed distance field soft shadows](http://advances.realtimerendering.com/s2015/DynamicOcclusionWithSignedDistanceFields.pdf) |
| [Triangle visibility buffer](https://diaryofagraphicsprogrammer.blogspot.com/2018/03/triangle-visibility-buffer.html) | It is a culling techniques used to only render what is necessary |
| Path tracer                                                  | A real-time raytracing renderer                              |

### Free middleware

With the release 1.48 of the forge, ConfettiFX made available for free some of the [middlewares](https://github.com/ConfettiFX/Custom-Middleware) it sells to game studios.

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Aura 3](https://github.com/ConfettiFX/Custom-Middleware/tree/master/Aura) | A global illumination system used in the game [Agents of Mayhem](https://en.wikipedia.org/wiki/Agents_of_Mayhem) |
| [Ephemeris 2](https://github.com/ConfettiFX/Custom-Middleware/tree/master/Ephemeris) | A skydome system used in the [Spiderman](https://en.wikipedia.org/wiki/Spider-Man_(2018_video_game)) game by Insomniac |

## Who maintains it ?

The development lead is [Wolfgang Engel](https://github.com/wolfgangfengel), a [famous head](https://en.wikipedia.org/wiki/Wolfgang_Engel) in the Computer Graphics field which used to be the Lead Graphics Programmer at Rockstar Games. He directed the book series [ShaderX, GPU Pro and now GPU Zen](https://www.realtimerendering.com/resources/shaderx/) which gather state of the art articles on various rendering techniques and optimisation. He has founded the company ConfettiFX in 2009, which works as consulting in the game industry.

The Confetti team provided tools and helped for various AAA games such as [Tomb Raider](https://en.wikipedia.org/wiki/Tomb_Raider_(2013_video_game)), [Battlefield 4](https://en.wikipedia.org/wiki/Battlefield_4), [Murdered Soul Suspect](https://en.wikipedia.org/wiki/Murdered:_Soul_Suspect), [Star Citizen](https://en.wikipedia.org/wiki/Star_Citizen), [Dirt 4](https://en.wikipedia.org/wiki/Dirt_4), [Mafia 3](https://en.wikipedia.org/wiki/Mafia_III), [Call of Duty Warzone](https://en.wikipedia.org/wiki/Call_of_Duty:_Warzone), [Spiderman](https://en.wikipedia.org/wiki/Spider-Man_(2018_video_game)), [Hades](https://en.wikipedia.org/wiki/Hades_(video_game)) and so on. They are experts in the computer graphics field for games. More details is available in their [yearly retrospective](https://theforge.dev/2020-a-retrospective/).

## Who uses it ?

### Bethesda - The elder scrolls VI / Starfield (2021+)

<img src="https://www.dexerto.fr/wp-content/uploads/sites/2/2020/03/un-leaker-de-the-elder-scroll-6-revele-une-possible-date-de-sortie-la-quete-principale-et-bien-plus-couv.jpg" width="450px">

Bethesda is currently developing their new in-house engine with The Forge as their rendering layer. Confetti is working with them for the integration and optimization.

### Un-announced Call of Duty mobile game (2021+)

<img src="https://cdn-uploads.gameblog.fr/images/jeux/hi/27478/CallofDutyBlackOpsColdWar_Multi_Editeur_006.jpg" width="450px">

TheForge is used as an Android / Vulkan runtime for a new Call of Duty game for smartphone.

### Facebook Business Framework (2021+)

<img src="https://www.itespresso.fr/wp-content/uploads/2016/06/facebook-messenger-application.jpg" width="450px">

Application framework by Facebook for smartphones using TheForge as their renderer. It is supposed to be run in 100s of million mobile devices.

### SuperGiant Games - Hades (2020)

<img src="https://www.jeuxvideo-live.com/images/news/illustrations/hades-grand-vainqueur-des-bafta-games-awards-2020-101880-large.jpg" width="450px">

The 2.5D game Hades is using TheForge as their rendering engine. They started to collaborate with Supergiant since 2014. TheForge integration with their tools started in April 2019 and ended in May 2020.

## What are the alternatives ?

> Other alternative such as [BGFX](https://github.com/bkaradzic/bgfx) or [Panda3D](https://www.panda3d.org/) are much higher level and do not belong in the same category

### [Diligent engine](https://github.com/DiligentGraphics/DiligentEngine)

Developed by [Egor Yusov](https://www.linkedin.com/in/egor-yusov/), previously a software engineer at Intel and Google, this library is thoroughly documented while offering a similar feature-set as TheForge. He provides articles on [Gamasutra](https://www.gamasutra.com/blogs/author/EgorYusov/1006649/) about his architecture choice.

### [Google Filament](https://github.com/google/filament)

Developed by Google as a rendering engine for their mobile devices and for the web. It is used as the Google Maps and Search AR backend.

## Why do we decided to use TheForge ?

Given its usage in the industry and the people behind it it was a no-brainer.