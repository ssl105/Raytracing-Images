# Background

These are images from my raytracer/pathtracer using Nvidia OptiX and CUDA. 

# Standard Raytracer

The images below are rendered from a standard raytracer using blinn-phong shading model. Shadows are handled by shooting a ray from the intersection point to the light sources. If an object is in the path of the ray, then the point is shaded as a shadow.

This image uses only an ambient color and does not fully utilize the blinn-phong model. 
![image1](images/hw1/scene4-ambient.png)

This image uses the diffuse portion of the shading model and you can see the shadows from the objects.
![image2](images/hw1/scene4-diffuse.png)

This image uses only the specular portion of the shading model. You can see the reflections off each object.
![image3](images/hw1/scene4-specular.png)

Here are some more images from more complicated scenes rendered with numerous objects in the scene. Additionally, the stanford dragon in the image below is constructed with 50,000 triangles.

![image4](images/hw1/scene5.png)

![image5](images/hw1/scene6.png)

![image6](images/hw1/scene7.png)

# Pathtracer

The difference between a pathtracer and a raytracer is that a pathtracer can shoot multiple rays per bounce and averages the results from the rays whereas a raytracer shoots only a single ray per bounce. Since a pathtracer uses more rays, it creates more detailed and realistic images compared to that of a standard raytracer.

## Direct Lighting

The images below focus on direct lighting from area light sources. Direct lighting involves two rays and one bounce. The first ray is drawn through a pixel from the camera/eye to some point in the scene. Then the ray bounces and another is theoretically drawn to the light source. Since we are dealing with an area light source, realistically the secodn ray could land anywhere with the light source. So to model this accurately, we can sample random points from the light source to draw our second ray. 

![image7](images/hw2/analytic.png)

![image8](images/hw2/direct9.png)

![image9](images/hw2/direct3x3.png)

![image10](images/hw2/sphere.png)

![image11](images/hw2/cornell.png)

![image12](images/hw2/dragon.png)
