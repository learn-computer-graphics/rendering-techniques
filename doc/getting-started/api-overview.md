# API Overview

## The application interface

Needed to use their windowing system

Talk about the macro `DEFINE_APPLICATION_MAIN` at the bottom of this file

Defined in the `OS` project

Not mandatory, possible to use SDL2 or GLFW, but latest game consoles not handled by these libs while they are with TheForge  

```c++
class IApp
{
public:
    // this pair of functions initializes and exits once during start-up and shut-down of the application
    // we open and close all the resources that will never change during the live span of an application
    // in other words, they are independent from any user changes to the device and quality settings
    // typically this is restricted to for example to loading and unloading geometry
	virtual bool Init() = 0;
	virtual void Exit() = 0;

    // this pair of functions loads and unloads everything that need to be re-loaded in case of a device change.
    // device changes can come from a user switching from hardware to Warp rendering support or switching on and off MSAA 
    // and other quality settings
    // typically shaders, textures, render targets and buffers are loaded here
	virtual bool Load() = 0;
	virtual void Unload() = 0;

    // this is input / math update -> everything CPU only ... no Graphics API calls
	virtual void Update(float deltaTime) = 0;
    
    // only Graphics API draw calls and command buffer generation
	virtual void Draw() = 0;

	virtual const char* GetName() = 0;
}
```

## Init

Need to create the renderer

### Queue families

### Command Pool

### Synchronisation primitives

#### Fences

#### Semaphores

### Samplers

### Resources

#### Textures

#### Models

### Shaders

#### Root Signature

#### Buffer Load Description

#### Descriptor sets

### UI

### User Inputs

## Load

### SwapChain

### DepthBuffer

### Graphics Pipeline Description

#### Vertex layout

#### Rasterizer State Description

#### Depth State Description

## Update

### Camera

### User inputs

### Uniforms local values

## Draw

### Swapchain

### Render target

### Synchronisation primitives

### Uniform buffers update

### Command generation

### Microprofiler markers

### Queue Submit

