# quick key
1. ctrl + f7--compile
# dependencies
## setting in vs2022
```mermaid
graph TD
A[project]-->B[properties]-->C[C/C++]
C-->D[General]-->E[Additional Include Directories]-->F["$(SolutionDir)"\\Dependencies\\GLFW\\include]
B-->G[Linker]-->General-->Additional_Library_Directories-->Input_file's_father_direcory-->H["$(SolutionDir)Dependencies\\GLFW\\lib-vc2022"]
G-->Input-->Additional_Dependencies-->glfw3.lib
F-->Include-->headfiles'_directory
```

## extern "C"
- translate C file or function in c into c++
```
extern "C" int glfwInit();
```


## Attention
1. library need to match your project's target platform