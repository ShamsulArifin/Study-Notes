Creating a real-time product configurator with the specified features in Unreal Engine is a substantial task, involving a combination of Blueprint scripting and C++ coding. Below is a more detailed guide on how you might approach each feature:

### 1. Import/Export 3D Models at Runtime:
- **Importing 3D Models:**
  - Use the `FAssetRegistryModule` to load a 3D model at runtime.
  - Refer to the [AssetRegistryModule documentation](https://docs.unrealengine.com/4.27/en-US/API/Runtime/AssetRegistry/IAssetRegistryModule/) for details.

- **Exporting 3D Models:**
  - Exporting 3D models at runtime is complex and may require custom logic using third-party libraries or C++ code. There isn't direct support for exporting static mesh data to an external file at runtime in Unreal Engine.

### 2. Import/Export 2D Images/Textures at Runtime:
- **Importing 2D Images/Textures:**
  - Use the `UTexture2D` class for dynamically creating textures at runtime.
  - Documentation: [Texture Import Guide](https://docs.unrealengine.com/4.27/en-US/Engine/TextureImportGuide/)

- **Exporting 2D Images/Textures:**
  - Exporting textures at runtime may require custom logic, such as saving the texture data to an external file.

### 3. Render High-Resolution Images in Real-Time and Export:
- **High-Resolution Rendering:**
  - Configure project settings for high resolution.
  - Use the `HighResShot` console command for capturing high-resolution screenshots.
  - Documentation: [High Resolution Screenshots](https://docs.unrealengine.com/4.27/en-US/Engine/Content/Types/Textures/HighResScreenshots/)
  
- **Exporting Rendered Images:**
  - Save the captured images to disk using C++. Consider Unreal's `FImageUtils` class for image manipulation.
  - Documentation: [FImageUtils](https://docs.unrealengine.com/4.27/en-US/API/Runtime/Core/Image/FImageUtils/)

### 4. Camera Settings for Viewport:
- **Camera Setup:**
  - Manipulate the camera settings using Blueprints or C++.
  - Documentation: [Camera Components](https://docs.unrealengine.com/4.27/en-US/Engine/Actors/CameraActors/)

### 5. Post-Processing Settings for Viewport:
- **Post-Processing Effects:**
  - Use post-processing volumes and materials to achieve desired effects.
  - Documentation: [Post Process Effects](https://docs.unrealengine.com/4.27/en-US/Engine/Rendering/PostProcessEffects/)

### 6. RTX Rendering Options:
- **Real-Time Ray Tracing (RTX):**
  - Ensure your project settings support RTX features.
  - Utilize console commands or C++ code to enable/disable RTX features at runtime.
  - Documentation: [Real-Time Ray Tracing](https://docs.unrealengine.com/4.27/en-US/Engine/Rendering/RayTracing/)

### Additional Tips:
- **Performance Optimization:**
  - Optimize your scenes for performance, especially when dealing with high-quality models and textures.

### Documentation Link:
- [Unreal Engine Documentation](https://docs.unrealengine.com/)

For more specific and up-to-date details, always refer to the official Unreal Engine documentation and community forums. Unreal Engine's documentation is comprehensive and can guide you through the implementation of various features in detail.