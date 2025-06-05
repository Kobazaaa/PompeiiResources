# 📦 Pompeii Resources

This repository contains models, textures, and potentially other asset files used by my main project: [Pompeii](https://github.com/Kobazaaa/Pompeii.git).
<br>
To see how these resources are used, check out the main repository as linked before.

## 📥 How to Use

Fetching the resources via CMake using FetchContent can be done as follows:

```cmake
include(FetchContent)

FetchContent_Declare(
    resourceRepo
    GIT_REPOSITORY https://github.com/Kobazaaa/PompeiiResources.git
    GIT_TAG        main
)
FetchContent_Populate(resourceRepo)

# Assets will be available at: ${resourceRepo_SOURCE_DIR}, at which point it is your responsibility to copy them to the correct destination, which could be done as follows:

add_custom_target(CopyTarget ALL
                COMMAND ${CMAKE_COMMAND} -E copy_directory
                        ${resourceRepo_SOURCE_DIR} ${DESTINATION_FOLDER}
                COMMENT "Copying folder from ${resourceRepo_SOURCE_DIR} to ${DESTINATION_FOLDER}."
                VERBATIM
)
# Add COPY_TARGET as a dependency to project 
add_dependencies(${TARGET_NAME} CopyTarget)

```

## 📄 License & Resources

Assets in this repository are subject to their respective licenses, which you can find under the "model licences" subdirectory.<br>

|Model| Format                                |Source|
|-----------|----------------------------------------|------------------|
|Sponza Crytek| .obj | Morgan McGuire's [Computer Graphics Archive](https://casual-effects.com/data). |
|Sponza| .gltf | Khronos Group's [glTF-Sample-Assets](https://github.com/KhronosGroup/glTF-Sample-Assets/tree/main/Models/Sponza). |
|A Beautiful Game| .gltf | Khronos Group's [glTF-Sample-Assets](https://github.com/KhronosGroup/glTF-Sample-Assets/tree/main/Models/ABeautifulGame). |
|Flight Helmet| .gltf | Khronos Group's [glTF-Sample-Assets](https://github.com/KhronosGroup/glTF-Sample-Assets/tree/main/Models/FlightHelmet). |
|Metal Rough Spheres| .gltf | Khronos Group's [glTF-Sample-Assets](https://github.com/KhronosGroup/glTF-Sample-Assets/tree/main/Models/MetalRoughSpheres). |
|HDRI Skybox Images| .hdr | Khronos Group's [glTF-Sample-Assets](https://polyhaven.com/). |

<br>
<br>
<br>

Created (and maintained) by Kobe Dereyne.
