# Computer Graphics Assignment - Animated Circle
-------------
Using **C++** with **OpenGL**, drawing a circle with a radius that is changing every frame.
- As shown in fig.1 :The circle is approximated by a set of triangles, We have v1,v2,v3,v4 and the center of the coordinate v0.

    When the **depth = 0**, We draw 4 triangles and the circle is nearly a square.
    
    When the **depth = 1**, each triangle is subdivided into two hence, we have 8 triangles.
### But given v1 and v2, how do we get v12 as case (b) is shown?
- Let’s consider v1, v2, and v12 as vectors. Then, v12 is in the direction of (v1 + v2) = (v1x+v2x, v1y+v2y,v1z+v2z) and the lengths
of the vectors are equal: |v1| = |v2| = |v12|.
- If the radius of the circle is one, then **_v12 = normalize (v1 + v2)_**.
> Normalizing a vector is like scaling the vector to a unit vector.

- In general, **_v12 = circleRadius * normalize(v1 + v2)_**, and every frame the program changes the value of circleRadius to make
the animation work.

> This subdivision process goes on depending on the value of the depth.

- Given a triangle with two vertices and the coordinate center,subdivideCircle() recursively subdivides the triangle depth times and draws 2<sup>depth</sup> triangles.

![alt text](https://imgur.com/QYfK0Oy.png "Circle of Triangles")