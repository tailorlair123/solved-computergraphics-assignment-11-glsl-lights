Download Link: https://assignmentchef.com/product/solved-computergraphics-assignment-11-glsl-lights
<br>
<span class="kksr-muted">Rate this product</span>

GLSL lights

In this assignment, you have to write the code for determining the light direction and color for 7 different illumination models. The application contained in index.html, has a user interface similar to the one of Example 04. Depending on the requested shader, the interface below changes to allow the user playing with the elements specific for the selected model. Shader code to compute the final pixel color should be written in file shaders.js. The code, written in GLSL, can use the following variables to find the elements necessary to compute the final color:

The shader can find the required information in the following variables:

vec3 fs_pos;

vec3 Pos;vec3 Dir;float ConeOut; float ConeIn; float Decay; float Target; vec4 lightColor;

vec4 ambientLightColor; vec4 ambientLightLowColor; vec3 ADir;vec4 SHconstColor;vec4 SHDeltaLxColor;vec4 SHDeltaLyColor;vec4 SHDeltaLzColor;

vec3 normalVec;The light direction is returned into:vec3 OlightDir;and intensity is returned into:vec4 OlightColor;ambient light contribution is returned into:vec4 ambientColor;The following GLSL standard procedure can be helpful in solving this exercise:

<pre>normalize()cos()radians()pow()</pre>

<pre>dot()length()clamp()reflect()max()</pre>

// Position of the point in 3D space

// Position of the light (if not direct)// Direction of the light (if not point)// Outer cone (in degree) of the light (if spot)// Inner cone (in percentage of the outher cone) of the light (if spot) // Decay factor (0, 1 or 2)// Target distance// color of the light

// Ambient light color. For hemispheric, this is the color on the top // For hemispheric ambient, this is the bottom color// For hemispheric ambient, this is the up direction// For spherical harmonics, constant term

// For spherical harmonics, DLx color // For spherical harmonics, DLy color // For spherical harmonics, DLz color

// direction of the normal vector to the surface

whose reference can be found at pages 7 and 8 of the official WebGL reference card from Kronos Group (webgl20-reference-guide.pdf, enclosed in this ZIP file for convenience).

GLSL will be presented in depth during the exercise sessions later in the course. However it has a syntax that is very similar to Javascript or C. Its main feature is having the possibility of operating on vectors and matrix with common math operators, and to extract vector components with the “.dot” notation (es: normalVec.x to denote the x component of the vector contained in variable normalVec). At this point, if you cannot figure out the syntax yourself, and you do not want to wait to have it covered in the course, you can refer to the following tutorial:

https://cgvr.cs.uni-bremen.de/teaching/cg2_07/literatur/glsl_tutorial/index.html

Starting from the section “Data Types and Variables”, at around 1/3 of the page. Please ignore what is presented before since it refers to a very old version of OpenGL which uses concepts that are now deprecated and not valid for WebGL.

To check the correctness of your shader, you can visually compare your results with the ones that can be obtained by Example E04, available on the Beep page of this course, after properly setting the same type of lights and materials.