# 📦 Project Resources

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

## 📄 License

Assets in this repository are subject to their respective licenses.

<br>
<br>
<br>

Maintained by Kobe Dereyne.