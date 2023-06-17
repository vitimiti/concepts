# C++ Concepts

A basic set of concepts to add on top of the existing standard ones.

## How to Use

Download the project and do
`target_include_directories(${PROJECT_NAME} PRIVATE ${path_to_project}/include`,
`target_link_libraries(${PROJECT_NAME} PRIVATE ${vitimiti_concepts})` to start using the concepts.

For example, if you want to use `FetchContent`, you may do:

```cmake
# Project definition...

include(FetchContent REQUIRED)

FetchContent_Declare(
        vitimiti_concepts
        GIT_REPOSITORY https://github.com/vitimiti/concepts.git
        GIT_TAG main)

FetchContent_MakeAvailable(vitimiti_concepts)

target_include_directories(${PROJECT_NAME} PRIVATE ${vitimiti_concepts_SOURCE_DIR}/include)
target_link_libraries(${PROJECT_NAME} PRIVATE ${vitimiti_concepts})

# Rest of the project configuration...
```

## Current Concepts

- `viti::concepts::integral_or_floating_point`: Defined as `std::is_integral_v<T> || std::is_floating_point_v<T>`, this
  concept is true when the given type is an integral or a floating point type.
