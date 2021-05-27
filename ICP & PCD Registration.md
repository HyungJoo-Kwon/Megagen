# ICP & PCD Registration

https://www.youtube.com/watch?v=dhzLQfDBx2Q

기존의 데이터셋에 현재 데이터를 Registration(정합)시키는 방법중의 하나로, 각 데이터들의 가장 가까운점을 이용하여 연관성을 찾고 그에 맞게 현재데이터를 이동 및 회전을 시켜 기존데이터셋에 추가하는 방법



Registration of 3D data points

- goal - find the parameters of the transformation that best align corresponding data points (find rotation matrix , translation vector)

- Optimization / search parameters

  - Iterative closest point (ICP)  - SVD를 기초로 함

  - Robust least squares approaches



Basic Alignment Problem

- Y = {![This is the rendered form of the equation. You can not edit this directly. Right click will give you the option to save the image, and in most browsers you can drag the image onto your desktop or another program.](https://latex.codecogs.com/gif.latex?y_%7B1%7D), ..., ![This is the rendered form of the equation. You can not edit this directly. Right click will give you the option to save the image, and in most browsers you can drag the image onto your desktop or another program.](https://latex.codecogs.com/gif.latex?y_%7Bi%7D)}, X = {![This is the rendered form of the equation. You can not edit this directly. Right click will give you the option to save the image, and in most browsers you can drag the image onto your desktop or another program.](https://latex.codecogs.com/gif.latex?x_%7B1%7D), ..., ![This is the rendered form of the equation. You can not edit this directly. Right click will give you the option to save the image, and in most browsers you can drag the image onto your desktop or another program.](https://latex.codecogs.com/gif.latex?x_%7Bj%7D)} with correspondences C = {(i, j)}

- Translation t and rotation R that minimize the sum of the squared errors

![This is the rendered form of the equation. You can not edit this directly. Right click will give you the option to save the image, and in most browsers you can drag the image onto your desktop or another program.](https://latex.codecogs.com/gif.latex?%5Csum_%7B%28i%2Cj%5C%29%20%5Cepsilon%20C%7D%5E%7B%7D%5Cleft%20%5C%7C%20y_%7Bi%7D%20-%20Rx_%7Bj%7D%20-t%20%5Cright%20%5C%7C%5E%7B2%7D%20%5Crightarrow%20min)

Simplified Correspondences

- reordering point clouds X, Y given correspondences C using an index N
  
  ![This is the rendered form of the equation. You can not edit this directly. Right click will give you the option to save the image, and in most browsers you can drag the image onto your desktop or another program.](https://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D_%7Bn%7D%20%3D%20Rx_%7Bn%7D%20&plus;%20t)





SVD - Based Alignment

![](./images/icp.PNG)

translate and rotate points : ![This is the rendered form of the equation. You can not edit this directly. Right click will give you the option to save the image, and in most browsers you can drag the image onto your desktop or another program.](https://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D_%7Bn%7D%20%3D%20Rx_%7Bn%7D%20&plus;%20t)     |     n = 1, ..., N