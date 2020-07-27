# Rendering Techniques

Explanation and examples of modern rendering techniques commonly used for game engines

## 🚩 Table of Contents

<details><summary>🧩 Show Classes</summary>
<p>

*(🏗️ : Not started | 📝 : Started | 📑 : Needs proofreading | ✔️ : Written )*

* Animation
  * [Skinning 🏗️]()
* Shading models
  * [Toon 🏗️]()
  * [Cook Torrance 🏗️]()
* Pipeline
  * [Deferred Rendering 🏗️]()
  * [Forward plus rendering 🏗️]()
* Optimisation
  * [Frustrum culling 🏗️]()
  * [Tesselation 🏗️]()
* Post Processing
  * [Motion Blur 🏗️]()
  * [Bloom 🏗️]()
  * [Depth of field 🏗️]()
* Shadows
  * [Shadow Mapping 🏗️]()
  * [Screen space ambiant occlusion 🏗️]()

</p>
</details>

## 👩‍💻 Getting Started

### Prerequisites

You can read the classes listed in the table of contents, but if you want to follow along, you need to install [CMake](https://cmake.org/) to build the project, and a C++ compiler which handles C++17.

#### Linux

```bash
sudo apt-get install build-essential cmake
```

#### Windows

To get the MSVC compiler, you need to install [Visual Studio](https://visualstudio.microsoft.com/) (and not VSCode), and select C++ development during installation.

### Build on desktop

You can handle the `CMakeLists.txt` in any way you like, here's some way to use it :

#### `Option 1: CLI`

Go to the folder of this project and run :

```bash
mkdir build
cd build
cmake ..
make
```

#### `Option 2: Visual Studio (Windows only)`

Open this folder with the `CMake...` option in file->open on Visual Studio, and run the project.

#### `Option 3: VSCode`

Use the `CMakeTools` plugin, build with `f7` then run with `f5` (But be careful to be on the right platform, there is a launch file for windows and for linux).

## 👨‍👩‍👦‍👦 Contributing

If you find errors in the code, or better way to explain or do things, feel free to open an issue !

## 📖 Sources

### Websites

| Name | Founder(s) | Description |
| --- | --- | --- |
| [WebGL Fundamentals](https://webglfundamentals.org/)         | -                                        | Various tutorial on rendering techniques for WebGL 1 & 2 |
| [Learn OpenGL](https://learnopengl.com/)                     | [Joey de Vries](http://joeydevries.com/) | Various tutorial on rendering techniques for OpenGL      |
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

### Videos

| Name | Author | Description |
| --- | --- | --- |
| [SketchPunkLabs - Learn WebGL](https://www.youtube.com/channel/UCSnyjB_8iVxi2ZAfn_1L6tA) | -      | Various tutorials on rendering techniques with WebGL     |
| [GDC Vault](https://www.gdcvault.com/free)                   | -      | Many conferences from professionals in the game industry |
| [The Cherno](https://www.youtube.com/channel/UCQ-W1KE9EYfdxhL6S4twUNw) | -      | Various videos on programming and graphics programming with content on OpenGL |
| [ChiliTomatoNoodle](https://www.youtube.com/user/ChiliTomatoNoodle) | - | Various videos on programming and graphics programming with content on DirectX |

### Repositories

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Sacha Willem's Vulkan](https://github.com/SaschaWillems/Vulkan) | Various rendering techniques with the Vulkan API             |
| [DirectX graphics samples](https://github.com/microsoft/DirectX-Graphics-Samples) | Microsoft official repository for code samples in DirectX 12 |
| [Vulkan Samples](https://github.com/KhronosGroup/Vulkan-Samples) | Khronos official repository for code samples in Vulkan       |

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

