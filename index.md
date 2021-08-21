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

The image below is rendered by using an analytical solution for quad light sources. There is no noise in the image, but analytical solution cannot be used in general since it does not consider shadows. For this project is used to create a reference image.
![image7](images/hw2/analytic.png)

The image below uses 9 random samples from the light source to determine the color of the ground surface. You can see that it is noisy compared to the reference solution above. 
![image8](images/hw2/direct9.png)

The image below uses 9 random samples as well, but the sampling is stratified. Stratified sampling in this case refers to dividing the area of the light source into 9 equal cells like a grid and taking a sample from each cell. This makes the resulting image more precise, but requires more calculations.
![image9](images/hw2/direct3x3.png)

Here are some more images rendered with accurate physics-based direct lighting using stratified sampling. Notice how the shadows differ from those produce by the raytracer. The edges of the shadow are softer because part of the light passes through from sampling. 

![image10](images/hw2/sphere.png)

![image11](images/hw2/cornell.png)

![image12](images/hw2/dragon.png)

## Indirect Lighting

![image13](images/hw3/cornellSimple.png)

![image14](images/hw3/cornellNEE.png)

![image15](images/hw3/cornellRR.png)

![image16](images/hw3/dragon.png)

## Importance Sampling

![image17](images/hw4/cornellCosine.png)

![image18](images/hw4/cornellBRDF.png)

![image19](images/hw4/ggx.png)

![image19](images/hw4/mis.png)

![image20](images/hw4/dragon.png)

