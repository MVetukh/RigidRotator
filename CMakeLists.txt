# Минимальная версия CMake
cmake_minimum_required(VERSION 3.10)

# Название проекта
project(QuantumRotor3D LANGUAGES CXX)

# Используем C++17
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Пути к заголовочным файлам
include_directories(${PROJECT_SOURCE_DIR}/include)

# Опции компиляции (для Linux/Windows)
if(MSVC)
    add_compile_options(/W4 /O2)
else()
    add_compile_options(-Wall -Wextra -O3)
endif()

# Источники
file(GLOB SRC_FILES
        "${PROJECT_SOURCE_DIR}/src/*.cpp"
)

# Создаём исполняемый файл
add_executable(quantum_rotor ${SRC_FILES})

# Если используешь Eigen (опционально)
# find_package(Eigen3 REQUIRED)
# target_link_libraries(quantum_rotor Eigen3::Eigen)


