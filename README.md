# 🔷 OpenGL Colored Square

This project renders a **colored square** using modern OpenGL in C++. It uses **shaders**, **vertex buffer objects**, **element buffer objects**, and a **modular structure** to separate concerns (Shader, VAO, VBO, EBO). The goal is to help understand how modern OpenGL works under the hood — including how vertex attributes like color and position are passed through the GPU pipeline.

---

## 🎯 What You'll Learn

- How to use **GLFW** to create an OpenGL context
- How to use **GLAD** to load OpenGL function pointers
- How to define and pass **vertex data**
- How to use **shaders** (GLSL) to render objects
- How to use **VBO**, **VAO**, and **EBO** in a clean, modular way
- How to render a **square with interpolated colors**

---

## 📸 Preview

![Screenshot](assets/colour%20rectangle.png)

---

## 📂 Project Structure

opengl-colored-square/
├── main.cpp # Main OpenGL code
├── ShaderClass.h # Shader loading and compiling
├── VAO.h # Vertex Array Object wrapper
├── VBO.h # Vertex Buffer Object wrapper
├── EBO.h # Element Buffer Object wrapper
├── default.vert # Vertex shader
├── default.frag # Fragment shader
└── README.md # You're here!


---

## 🛠️ Setup Instructions

### ✅ Prerequisites
Make sure you have installed:

- [GLFW](https://www.glfw.org/)
- [GLAD](https://glad.dav1d.de/) (set to OpenGL 3.3 Core)
- OpenGL (comes with your GPU drivers)
- A C++17 compatible compiler (g++, clang++, MSVC)

---

### 🧑‍💻 Compile & Run

#### On Linux/macOS (with g++)
```bash
g++ main.cpp -o OpenGLApp -lglfw -ldl -lGL
./OpenGLApp
On Windows (MinGW)
g++ main.cpp -o OpenGLApp -Iinclude -Llib -lglfw3 -lopengl32 -lgdi32

📌 Note: Make sure glad.c is also compiled and linked, and that shader files are in the same folder as your .exe or working directory.

### 🖼️ Shaders
-🧱 default.vert – Vertex Shader
#version 330 core
layout (location = 0) in vec3 aPos;
layout (location = 1) in vec3 aColor;

out vec3 ourColor;

void main() {
    gl_Position = vec4(aPos, 1.0);
    ourColor = aColor;
}

 default.frag – Fragment Shader

#version 330 core
in vec3 ourColor;
out vec4 FragColor;

void main() {
    FragColor = vec4(ourColor, 1.0);
}

✍️ Code Highlights
🔹 Vertex Data

GLfloat vertices[] = {
    // Positions         // Colors
     0.5f,  0.5f, 0.0f,   1.0f, 0.0f, 0.0f,  // Top Right (Red)
     0.5f, -0.5f, 0.0f,   0.0f, 1.0f, 0.0f,  // Bottom Right (Green)
    -0.5f, -0.5f, 0.0f,   0.0f, 0.0f, 1.0f,  // Bottom Left (Blue)
    -0.5f,  0.5f, 0.0f,   1.0f, 1.0f, 0.0f   // Top Left (Yellow)
};
🔹 Indices (EBO)
GLuint indices[] = {
    0, 1, 3,  // Triangle 1
    1, 2, 3   // Triangle 2
};



📌 Future Improvements

    Add texture support

    Add camera and 3D perspective

    Convert into a spinning cube

    Build a basic OpenGL game loop



🧾 License

This project is open source under the MIT License. Feel free to use and modify.
---

### 📦 Want a zip or repo template version of this too?
I can prepare that or even generate a CMake version if you're planning to scale up the project.

Let me know if you'd like:
- A **rotating square**
- A **textured square**
- Or to turn this into a **game engine starter template**

Ready when you are!
