# Rendering Techniques

Explanation and examples of modern rendering techniques commonly used for game engines

## 🚩 Table of Contents

<details><summary>🧩 Show Classes</summary>
<p>

*(🏗️ : Not started | 📝 : Started | 📑 : Needs proofreading | ✔️ : Written )*

* Todo
  * [Skinning 🏗️]()
* Todo
  * [Deferred Rendering 🏗️]()

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

### Videos

| Name | Author | Description |
| --- | --- | --- |
| [SketchPunkLabs - Learn WebGL](https://www.youtube.com/channel/UCSnyjB_8iVxi2ZAfn_1L6tA) | -      | Various tutorials on rendering techniques with WebGL     |
| [GDC Vault](https://www.gdcvault.com/free)                   | -      | Many conferences from professionals in the game industry |
| [The Cherno](https://www.youtube.com/channel/UCQ-W1KE9EYfdxhL6S4twUNw) | -      | Various videos on programming and graphics programming   |

### Books

| Name                                                         | Description                                                  | Illustration |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------ |
| [Game Engine Architecture](https://www.gameenginebook.com/)  | A famous book by Jason Gregory, a Naughty Dog engineer       |              |
| [Real Time Rendering](http://www.realtimerendering.com/book.html) | Famous book on rendering techniques                          |              |
| [Game Programming Gems Serie](http://www.satori.org/game-programming-gems/) | Mark DeLoura compilation of articles by other developers     |              |
| [GPU Gems Serie](https://developer.nvidia.com/gpugems/gpugems/contributors) | Compilation of various articles by developers                |              |
| [GPU Pro Serie](http://gpupro.blogspot.com/)                 | [Wolfgang Engel](http://www.blogger.com/profile/11031097395025597662) compilation of articles by other developers |              |
| [Game Engine Gems Serie](http://www.gameenginegems.net/)     | Compilation of articles by developers                        |              |
| [Fundamentals of Computer Graphics](https://www.oreilly.com/library/view/fundamentals-of-computer/9781482229417/) | A broad book explaining computer graphics from scratch       |              |
| [Physically Based Rendering](http://www.pbr-book.org/)       | Matt Pharr, Wenzel Jakob, and Greg Humphreys revolutionary book on materials |              |

