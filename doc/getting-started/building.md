# Building TheForge

ConfettiFX provides IDE project files for each of the platforms it supports. These are located in [`Examples_3/Unit_Tests/YOUR_PLATFORM`](https://github.com/ConfettiFX/The-Forge/tree/master/Examples_3/Unit_Tests). For free we have access to (other platforms are only available for accredited developers) :

- XCode for MacOS
- Visual Studio 2017 for Android ([can be upgraded to 2019 on open](https://github.com/ConfettiFX/The-Forge/issues/137))
- Visual Studio 2017 for Windows ([can be upgraded to 2019 on open](https://github.com/ConfettiFX/The-Forge/issues/137))
- Codeline for Linux

The project do not officially support project generator tools such as [CMake](https://cmake.org/), [Premake](https://premake.github.io/) or even [Sharpmake](https://github.com/ubisoft/Sharpmake), which means that it can be cumberstone to create a new project or integrate the library into your pipeline.

As an open-source project, the community have since created more streamlined version of the library to use standard project generation. You have the multiple choice to build our samples :

## `Option 1:` Use our custom, simplified project

We provide a repository called [The-Forge-Samples](https://github.com/learn-computer-graphics/the-forge-samples) from which you will find detailed build instruction for your platform. It uses CMake for project generation so you will be able to generate project file for your favorite IDE.

## `Option 2:` Use the official TheForge repository

As explained above, ConfettiFX provides project files for some IDEs which works just fine. Yet If you want to create another project from it there are multiple configuration steps to do. 

We will focus on the Windows platform as it is the most used, but the setup will be equivalent for the Other IDEs. 

### Prerequisites (Windows)

You need to install [Visual Studio](https://visualstudio.microsoft.com/fr/) and select the C/C++ development package.

Then you can download The-Forge project from their repository. Either as a .zip file or by running `git clone https://github.com/ConfettiFX/The-Forge.git`

To run the unit test, you have to download the assets used by the examples. To do so simply run the `PRE_BUILD.bat` file.

Then open the Visual Studio project located in `The-Forge\Examples_3\Unit_Tests\PC Visual Studio 2017\Unit_Tests.sln`. You will probably have a more recent visual studio version, so you will have a popup to upgrade the project. Select yes.

In the Project Browser, right click on `Examples\01_Transformations` end set it as startup project.

Finally, on the upper window select build config to `DebugDx` and launch the build.

If you have no error, the following window with asteroids should open.

Now if you want to follow along our tutorial from TheForge official repository there are essentially two ways to go :

### `Option A:` Modify an existing example

Simply remove the content of the .cpp file of an Unit Test of your choice and follow the tutorial. There might be other things to change, such as shader files or resource files.

### `Option B:` Create a new Visual Studio project inside the unit test solution

#### 1. Create a new project

Right click and create new project

Set the name to DebugDx or file won't be copied

#### 2. Copy resources in local folder

Shaders and GPUCfg in the same folder in src

Add them with add existing files

#### 3. Link Libraries

In `Configuration Properties/VC++ Directories/Library Directories`

```
$(SolutionDir)\$(Platform)\$(Configuration);$(LibraryPath)
```

In `Configuration Properties/Linker/Input/Additional Dependencies`

```
LuaManager.lib;Xinput9_1_0.lib;ws2_32.lib;gainputstatic.lib;RendererDX12.lib;OS.lib;%(AdditionalDependencies)
```

In `Configuration Properties/Linker/General/Additional Library Directories`

```
$(GLFW_DIR)\lib
```

#### 4. Post-build commands to copy resources to build folder

In `Configuration Properties/Build Events/Post-build Event`

```bash
set SHADER_DIR=D3D12
if $(Configuration) == DebugDx11 set SHADER_DIR=D3D11
if $(Configuration) == ReleaseDx11 set SHADER_DIR=D3D11
if $(Configuration) == DebugVk set SHADER_DIR=Vulkan
if $(Configuration) == ReleaseVk set SHADER_DIR=Vulkan

xcopy /Y /S /D "$(ProjectDir)..\UnitTestResources\Textures\Skybox_*.dds" "$(OutDir)Textures\"
xcopy /Y /S /D "$(ProjectDir)..\UnitTestResources\Textures\circlepad.dds" "$(OutDir)Textures\"
xcopy /Y /S /D "$(ProjectDir)..\UnitTestResources\Fonts\*.ttf" "$(OutDir)Fonts\"
xcopy /Y /S /D "$(ProjectDir)..\UnitTestResources\Fonts\*.otf" "$(OutDir)Fonts\"
xcopy /Y /S /D "$(ProjectDir)..\..\..\Middleware_3\UI\Shaders\%SHADER_DIR%\*.*" "$(OutDir)Shaders\"
xcopy /Y /S /D "$(ProjectDir)..\..\..\Middleware_3\Text\Shaders\%SHADER_DIR%\*.*" "$(OutDir)Shaders\"
xcopy /Y /S /D "$(ProjectDir)..\src\$(ProjectName)\Shaders\%SHADER_DIR%\*.*" "$(OutDir)Shaders\"
xcopy /Y /S /D "$(ProjectDir)..\src\$(ProjectName)\GPUCfg\*.*" "$(OutDir)GPUCfg\"

xcopy /Y /D "$(SolutionDir)$(Platform)\$(Configuration)\*.dll" "$(OutDir)"
```

Note that the `CompiledShader` folder is created at runtime if shader compiled not found

#### 5. Set project build order

With dependencies on master project properties

```
With a community CMakegainputstatic
LuaManager
OS
RendererDX11
RendererDX12
RendererVulkan
```

