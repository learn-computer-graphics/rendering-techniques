# Building TheForge

Does not officially support project generator. They provide IDE files for each platform.

Project can be found in `The-Forge\Examples_3\Unit_Tests\PC Visual Studio 2017\Unit_Tests.sln` set `Examples\01_Transformations` as startup project. Set build to DebugDx

## By modifying directly the example

Simply remove the content of the first .cpp and follow the tutorial

## With a new Visual Studio project

### Create a new project

Right click and create new project

Set the name to DebugDx or file won't be copied

### Copy resources in local folder

Shaders and GPUCfg in the same folder in src

Add them with add existing files

### Link Libraries

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

### Post-build commands to copy resources to build folder

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

### Set project build order

With dependencies on master project properties

```
gainputstatic
LuaManager
OS
RendererDX11
RendererDX12
RendererVulkan
```

## With a community CMake

https://github.com/rextimmy/the-forge-glfw

