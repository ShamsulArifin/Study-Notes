Creating a product configurator with such detailed features in Unreal Engine involves a combination of Blueprint scripting and, possibly, C++ coding. Here's a more detailed breakdown of each feature and relevant documentation links:

### 1. Import/Export 3D Models at Runtime:
- **Importing 3D Models:**
  - Use the `UAssetImportData` class for handling asset import settings. 
  - Documentation: [Importing Content](https://docs.unrealengine.com/4.27/en-US/ProductionPipelines/Importing/)
  
- **Exporting 3D Models:**
  - Exporting 3D models at runtime is more complex and might require using third-party libraries or writing custom C++ code to handle the export process.
  
### 2. Import/Export 2D Images/Textures at Runtime:
- **Importing 2D Images/Textures:**
  - Use the `UTexture2D` class for dynamically creating textures at runtime.
  - Documentation: [Texture Import Guide](https://docs.unrealengine.com/4.27/en-US/Engine/TextureImportGuide/)
  
- **Exporting 2D Images/Textures:**
  - Similar to 3D models, exporting textures at runtime may require custom logic or third-party libraries.

### 3. Render High-Resolution Images in Real-Time and Export:
- **High-Resolution Rendering:**
  - Configure project settings for high resolution.
  - Utilize the `HighResShot` console command for capturing high-resolution screenshots.
  - Documentation: [High Resolution Screenshots](https://docs.unrealengine.com/4.27/en-US/Engine/Content/Types/Textures/HighResScreenshots/)
  
- **Exporting Rendered Images:**
  - You might need to use C++ to save the captured images to disk.
  - Refer to Unreal's `FImageUtils` class for image manipulation.
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
  - Documentation: [Real-Time Ray Tracing](https://docs.unrealengine.com/4.27/en-US/Engine/Rendering/RayTracing/)

### Additional Tips:
- **Performance Optimization:**
  - Optimize your scenes for performance, especially if you're using high-quality models and textures.

### Documentation Link:
- [Unreal Engine Documentation](https://docs.unrealengine.com/)

For more specific and up-to-date details, always refer to the official Unreal Engine documentation and community forums. Unreal Engine's documentation is comprehensive and can guide you through the implementation of various features in detail.