# The Forge

<img src="https://github.com/ConfettiFX/The-Forge/raw/master/Screenshots/The%20Forge%20-%20Colour%20Black%20Landscape.png" width="150px" />

## What is The Forge ?

 <a href='https://github.com/ConfettiFX/The-Forge' target='_blank'>The Forge</a> is a cross-platform rendering framework developed by  <a href='https://theforge.dev/' target='_blank'>ConfettiFX</a>. It's role is to  <a href='https://github.com/ConfettiFX/The-Forge/issues/99' target='_blank'>ease the developer's burden</a> when it comes to render things on screen. It is a low-level abstraction layer for the modern Graphic APIs such as  <a href='https://en.wikipedia.org/wiki/DirectX' target='_blank'>DirectX12</a> and  <a href='https://en.wikipedia.org/wiki/Vulkan_(API' target='_blank'>Vulkan</a>). For accredited developers, it can also support all major game consoles (Xbox, Playstation 5, Switch, etc). With The Forge, write once, run (almost) everywhere. 

Compared to an in-house project, using this library is the guarantee to have a more stable solution, field tested and with a clear and concise API validated by veteran of the industry.  The first official release was done in 2018, so it's fair to say that the codebase is quite recent. In the few years of development that followed, the maintainers at ConfettiFX added multiple features in the engine related to the work they do as consultants for external game studios.

### Some engine features

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Custom Entity Component System ( <a href='https://github.com/guillaume-haerinck/met-ecs' target='_blank'>ECS</a>) | The  <a href='https://docs.unity3d.com/Packages/com.unity.entities@0.16/manual/index.html' target='_blank'>ECS</a> programming pattern is a quite recent paradigm which provide a code structure better suited for performance and parallelism. They developed an in-house ECS which can be integrated easily in the rendering engine. |
| Cross-platform file system                                   | The inclusion of a platform-agnostic standard library to handle filesystem in C++ is recent (v17), so they provide a C-like API which is guarantee to work on any platforms The Forge runs on. |
|  <a href='https://github.com/ConfettiFX/The-Forge/wiki/Microprofiler---How-to-Use' target='_blank'>Micro profiler</a> | One of the main goal of a library like The Forge is performance, so it is crucial to be able to monitor it easily and this is exactly what this tool is for. |
|  <a href='https://github.com/ConfettiFX/The-Forge/wiki/The-Forge-Shading-Language-(FSL' target='_blank'>Global shading language</a>) | Multiple APIs uses multiple shading languages. With TheForge it is possible to write every shader with a superset of HLSL called FSL, and a translator will take care of translating the FSL to the API in use. |
| Multi-threaded rendering                                     | One of the goal of the new Graphic API, besides being closer to the metal, is to be suited for multi-threading environments. TheForge keeps this particularity and handle multi-threaded command buffer generation as well as async and multi-threaded resource loading. |
|  <a href='https://github.com/ConfettiFX/The-Forge/wiki/Input-System-Overview' target='_blank'>Input handling</a> | They provide an input-handling API similar to what is available in Unity in C#. |
| LUA Scripting                                                | It is possible to use basic scripting to animate objects, lights and cameras. |

### Some visual features

The support for  <a href='https://developer.nvidia.com/blog/introduction-turing-mesh-shaders/' target='_blank'>Mesh Shaders</a> (which are growing to be a game-changer as seen with  <a href='https://docs.unrealengine.com/5.0/en-US/RenderingFeatures/Nanite/' target='_blank'>Unreal Engine 5 Nanite</a> renderer) is on its way but  <a href='https://github.com/ConfettiFX/The-Forge/issues/174' target='_blank'>not there yet</a>.

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Custom debug UI                                              | They provide a custom ui system based on  <a href='https://github.com/ocornut/imgui' target='_blank'>ImGui</a>. |
| Skinning animation system                                    | It is based on based on the library  <a href='https://github.com/guillaumeblanc/ozz-animation' target='_blank'>OZZ</a> and also support invert kinematic and joints. |
| Sparse Virtual Textures                                      | The Forge is able to use very large textures, the idea is that only the visible portion is loaded on the GPU. |
|  <a href='https://www.amd.com/fr/technologies/tressfx' target='_blank'>TressFX</a> by AMD | A real-time hair rendering system that they helped developed. It was used for the  <a href='https://en.wikipedia.org/wiki/Tomb_Raider_(2013_video_game' target='_blank'>Tomb Raider</a>) game in 2013 |
| Multiple shadow map generation systems                       | They support  <a href='https://pixelstoomany.wordpress.com/category/shadows/exponential-shadow-maps/' target='_blank'>exponential shadow map</a>,  <a href='http://gpuzen.blogspot.com/2019/05/gpu-zen-2-parallax-corrected-cached.html' target='_blank'>adaptive shadow map with parallax correction cache</a> and  <a href='http://advances.realtimerendering.com/s2015/DynamicOcclusionWithSignedDistanceFields.pdf' target='_blank'>signed distance field soft shadows</a> |
|  <a href='https://diaryofagraphicsprogrammer.blogspot.com/2018/03/triangle-visibility-buffer.html' target='_blank'>Triangle visibility buffer</a> | It is a culling techniques used to only render what is necessary |
| Path tracer                                                  | A real-time raytracing renderer                              |

### Free middleware

With the release 1.48 of the forge, ConfettiFX made available for free some of the  <a href='https://github.com/ConfettiFX/Custom-Middleware' target='_blank'>middlewares</a> it sells to game studios.

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|  <a href='https://github.com/ConfettiFX/Custom-Middleware/tree/master/Aura' target='_blank'>Aura 3</a> | A global illumination system used in the game  <a href='https://en.wikipedia.org/wiki/Agents_of_Mayhem' target='_blank'>Agents of Mayhem</a> |
|  <a href='https://github.com/ConfettiFX/Custom-Middleware/tree/master/Ephemeris' target='_blank'>Ephemeris 2</a> | A skydome system used in the  <a href='https://en.wikipedia.org/wiki/Spider-Man_(2018_video_game' target='_blank'>Spiderman</a>) game by Insomniac |

## Who maintains it ?

The development lead is  <a href='https://github.com/wolfgangfengel' target='_blank'>Wolfgang Engel</a>, a  <a href='https://en.wikipedia.org/wiki/Wolfgang_Engel' target='_blank'>famous head</a> in the Computer Graphics field which used to be the Lead Graphics Programmer at Rockstar Games. He directed the book series  <a href='https://www.realtimerendering.com/resources/shaderx/' target='_blank'>ShaderX, GPU Pro and now GPU Zen</a> which gather state of the art articles on various rendering techniques and optimisation. He has founded the company ConfettiFX in 2009, which works as consulting in the game industry.

The Confetti team provided tools and helped for various AAA games such as  <a href='https://en.wikipedia.org/wiki/Tomb_Raider_(2013_video_game' target='_blank'>Tomb Raider</a>),  <a href='https://en.wikipedia.org/wiki/Battlefield_4' target='_blank'>Battlefield 4</a>,  <a href='https://en.wikipedia.org/wiki/Murdered:_Soul_Suspect' target='_blank'>Murdered Soul Suspect</a>,  <a href='https://en.wikipedia.org/wiki/Star_Citizen' target='_blank'>Star Citizen</a>,  <a href='https://en.wikipedia.org/wiki/Dirt_4' target='_blank'>Dirt 4</a>,  <a href='https://en.wikipedia.org/wiki/Mafia_III' target='_blank'>Mafia 3</a>,  <a href='https://en.wikipedia.org/wiki/Call_of_Duty:_Warzone' target='_blank'>Call of Duty Warzone</a>,  <a href='https://en.wikipedia.org/wiki/Spider-Man_(2018_video_game' target='_blank'>Spiderman</a>),  <a href='https://en.wikipedia.org/wiki/Hades_(video_game' target='_blank'>Hades</a>) and so on. They are experts in the computer graphics field for games. More details is available in their  <a href='https://theforge.dev/2020-a-retrospective/' target='_blank'>yearly retrospective</a>.

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

> Other alternative such as  <a href='https://github.com/bkaradzic/bgfx' target='_blank'>BGFX</a> or  <a href='https://www.panda3d.org/' target='_blank'>Panda3D</a> are much higher level and do not belong in the same category

###  <a href='https://github.com/DiligentGraphics/DiligentEngine' target='_blank'>Diligent engine</a>

Developed by  <a href='https://www.linkedin.com/in/egor-yusov/' target='_blank'>Egor Yusov</a>, previously a software engineer at Intel and Google, this library is thoroughly documented while offering a similar feature-set as TheForge. He provides articles on  <a href='https://www.gamasutra.com/blogs/author/EgorYusov/1006649/' target='_blank'>Gamasutra</a> about his architecture choice.

###  <a href='https://github.com/google/filament' target='_blank'>Google Filament</a>

Developed by Google as a rendering engine for their mobile devices and for the web. It is used as the Google Maps and Search AR backend.

## Why do we decided to use TheForge ?

Given its usage in the industry and the people behind it it was a no-brainer.