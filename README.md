# WebGL Path Tracing

![](http://evanw.github.com/webgl-path-tracing/image.png)

[Try it live](http://madebyevan.com/webgl-path-tracing/) (requires a browser with WebGL)

Path tracing is a realistic lighting algorithm that simulates light bouncing around a scene. This path tracer uses WebGL for realtime performance and supports diffuse, mirrored, and glossy surfaces. The path tracer is continually rendering, so the scene will start off grainy and become smoother over time.

The entire scene is dynamically compiled into a GLSL shader. Everything can be repositioned using the current shader, but any geometry or material change means a recompilation. To calculate a pixel color, a ray is shot into the scene and allowed to bounce around five times. At each bounce, the direct light incoming at that point (including shadows) is multiplied by all previous material colors and accumulated. Soft shadows are achieved by randomly jittering the light position per-pixel.
