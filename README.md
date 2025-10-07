# 🖼️ Edge Detection using Prewitt, Roberts, and Sobel Operators (MATLAB)

![MATLAB](https://img.shields.io/badge/MATLAB-R2020a+-orange?logo=mathworks)
![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Image Processing](https://img.shields.io/badge/Image%20Processing-Edge%20Detection-brightgreen)

---

## 📘 Project Overview

This project demonstrates **edge detection techniques** using three classical gradient-based operators — **Prewitt**, **Roberts**, and **Sobel** — implemented in **MATLAB**.  
The goal is to **compare** how each operator detects horizontal, vertical, and combined edges across multiple images.

Each operator is applied to the following **three images**:
- `exp5_img.jpg` (Old Image)  
- `Finger.png` (New Image)  
- `without_back.jpg` (New 2 Image)

The output figure displays a **3×5 grid**, showing:
| Original | Grayscale | Gx (Horizontal) | Gy (Vertical) | Combined (Gx + Gy) |

---

## ⚙️ Techniques Implemented

### 🔹 Code 1 – Prewitt Operator (`edge_prewitt.m`)

```matlab
% Read images and resize them
a = imread("exp5_img.jpg");
b = imresize(a, [512, 512]);
a_new = imread("Finger.png");
b_new = imresize(a_new, [512, 512]);
a_new2 = imread("without_back.jpg");
b_new2 = imresize(a_new2, [512, 512]);

% Create a figure and specify its size
figure('Position', [100, 100, 1500, 800]);

% Image 1 (Old)
subplot(3, 5, 1);
imshow(b);
title('Og Img(Old)');
I = rgb2gray(b);
subplot(3, 5, 2);
imshow(I);
title('Gray Img(Old)');
Gx = edge(I, 'Prewitt', [], 'horizontal');
Gy = edge(I, 'Prewitt', [], 'vertical');
subplot(3, 5, 3);
imshow(Gx);
title('Grad Gx(Old)');
subplot(3, 5, 4);
imshow(Gy);
title('Grad Gy(Old)');
G = sqrt(double(Gx).^2 + double(Gy).^2);
G = uint8(G * (255 / max(G(:))));
subplot(3, 5, 5);
imshow(G);
title('Grad Gx + Gy(Old)');

% Image 2 (New)
subplot(3, 5, 6);
imshow(b_new);
title('Og Img(New)');
I_new = rgb2gray(b_new);
subplot(3, 5, 7);
imshow(I_new);
title('Gray Img(New)');
Gx_new = edge(I_new, 'Prewitt', [], 'horizontal');
Gy_new = edge(I_new, 'Prewitt', [], 'vertical');
subplot(3, 5, 8);
imshow(Gx_new);
title('Grad Gx(New)');
subplot(3, 5, 9);
imshow(Gy_new);
title('Grad Gy(New)');
G_new = sqrt(double(Gx_new).^2 + double(Gy_new).^2);
G_new = uint8(G_new * (255 / max(G_new(:))));
subplot(3, 5, 10);
imshow(G_new);
title('Grad Gx + Gy(New)');

% Image 3 (New 2)
subplot(3, 5, 11);
imshow(b_new2);
title('Og Img(New 2)');
I_new2 = rgb2gray(b_new2);
subplot(3, 5, 12);
imshow(I_new2);
title('Gray Img(New 2)');
Gx_new2 = edge(I_new2, 'Prewitt', [], 'horizontal');
Gy_new2 = edge(I_new2, 'Prewitt', [], 'vertical');
subplot(3, 5, 13);
imshow(Gx_new2);
title('Grad Gx(New 2)');
subplot(3, 5, 14);
imshow(Gy_new2);
title('Grad Gy(New 2)');
G_new2 = sqrt(double(Gx_new2).^2 + double(Gy_new2).^2);
G_new2 = uint8(G_new2 * (255 / max(G_new2(:))));
subplot(3, 5, 15);
imshow(G_new2);
title('Grad Gx + Gy(New 2)');

sgtitle('Edge Detection Results using Prewitt Operator', 'FontSize', 14);
````
<img width="1877" height="788" alt="image" src="https://github.com/user-attachments/assets/b1fdb8ba-4ce1-436a-b22f-974c602d2178" />

---

### 🔹 Code 2 – Roberts Operator (`edge_roberts.m`)

```matlab
% Read images and resize them
a = imread("exp5_img.jpg");
b = imresize(a, [512, 512]);
a_new = imread("Finger.png");
b_new = imresize(a_new, [512, 512]);
a_new2 = imread("without_back.jpg");
b_new2 = imresize(a_new2, [512, 512]);

figure('Position', [100, 100, 1500, 800]);

% Image 1 (Old)
subplot(3, 5, 1);
imshow(b);
title('Og Img(Old)');
I = rgb2gray(b);
subplot(3, 5, 2);
imshow(I);
title('Gray Img(Old)');
Gx = edge(I, 'Roberts', [], 'horizontal');
Gy = edge(I, 'Roberts', [], 'vertical');
subplot(3, 5, 3);
imshow(Gx);
title('Grad Gx(Old)');
subplot(3, 5, 4);
imshow(Gy);
title('Grad Gy(Old)');
G = sqrt(double(Gx).^2 + double(Gy).^2);
G = uint8(G * (255 / max(G(:))));
subplot(3, 5, 5);
imshow(G);
title('Grad Gx + Gy(Old)');

% Image 2 (New)
subplot(3, 5, 6);
imshow(b_new);
title('Og Img(New)');
I_new = rgb2gray(b_new);
subplot(3, 5, 7);
imshow(I_new);
title('Gray Img(New)');
Gx_new = edge(I_new, 'Roberts', [], 'horizontal');
Gy_new = edge(I_new, 'Roberts', [], 'vertical');
subplot(3, 5, 8);
imshow(Gx_new);
title('Grad Gx(New)');
subplot(3, 5, 9);
imshow(Gy_new);
title('Grad Gy(New)');
G_new = sqrt(double(Gx_new).^2 + double(Gy_new).^2);
G_new = uint8(G_new * (255 / max(G_new(:))));
subplot(3, 5, 10);
imshow(G_new);
title('Grad Gx + Gy(New)');

% Image 3 (New 2)
subplot(3, 5, 11);
imshow(b_new2);
title('Og Img(New 2)');
I_new2 = rgb2gray(b_new2);
subplot(3, 5, 12);
imshow(I_new2);
title('Gray Img(New 2)');
Gx_new2 = edge(I_new2, 'Roberts', [], 'horizontal');
Gy_new2 = edge(I_new2, 'Roberts', [], 'vertical');
subplot(3, 5, 13);
imshow(Gx_new2);
title('Grad Gx(New 2)');
subplot(3, 5, 14);
imshow(Gy_new2);
title('Grad Gy(New 2)');
G_new2 = sqrt(double(Gx_new2).^2 + double(Gy_new2).^2);
G_new2 = uint8(G_new2 * (255 / max(G_new2(:))));
subplot(3, 5, 15);
imshow(G_new2);
title('Grad Gx + Gy(New 2)');

sgtitle('Edge Detection Results using Roberts Operator', 'FontSize', 14);
```
<img width="1875" height="794" alt="image" src="https://github.com/user-attachments/assets/c9b04555-2787-4ce3-8894-293866c754cf" />

---

### 🔹 Code 3 – Sobel Operator (`edge_sobel.m`)

```matlab
% Read images and resize them
a = imread("exp5_img.jpg");
b = imresize(a, [512, 512]);
a_new = imread("Finger.png");
b_new = imresize(a_new, [512, 512]);
a_new2 = imread("without_back.jpg");
b_new2 = imresize(a_new2, [512, 512]);

figure('Position', [100, 100, 1500, 800]);

% Image 1 (Old)
subplot(3, 5, 1);
imshow(b);
title('Og Img(Old)');
I = rgb2gray(b);
subplot(3, 5, 2);
imshow(I);
title('Gray Img(Old)');
Gx = edge(I, 'Sobel', [], 'horizontal');
Gy = edge(I, 'Sobel', [], 'vertical');
subplot(3, 5, 3);
imshow(Gx);
title('Grad Gx(Old)');
subplot(3, 5, 4);
imshow(Gy);
title('Grad Gy(Old)');
G = sqrt(double(Gx).^2 + double(Gy).^2);
G = uint8(G * (255 / max(G(:))));
subplot(3, 5, 5);
imshow(G);
title('Grad Gx + Gy(Old)');

% Image 2 (New)
subplot(3, 5, 6);
imshow(b_new);
title('Og Img(New)');
I_new = rgb2gray(b_new);
subplot(3, 5, 7);
imshow(I_new);
title('Gray Img(New)');
Gx_new = edge(I_new, 'Sobel', [], 'horizontal');
Gy_new = edge(I_new, 'Sobel', [], 'vertical');
subplot(3, 5, 8);
imshow(Gx_new);
title('Grad Gx(New)');
subplot(3, 5, 9);
imshow(Gy_new);
title('Grad Gy(New)');
G_new = sqrt(double(Gx_new).^2 + double(Gy_new).^2);
G_new = uint8(G_new * (255 / max(G_new(:))));
subplot(3, 5, 10);
imshow(G_new);
title('Grad Gx + Gy(New)');

% Image 3 (New 2)
subplot(3, 5, 11);
imshow(b_new2);
title('Og Img(New 2)');
I_new2 = rgb2gray(b_new2);
subplot(3, 5, 12);
imshow(I_new2);
title('Gray Img(New 2)');
Gx_new2 = edge(I_new2, 'Sobel', [], 'horizontal');
Gy_new2 = edge(I_new2, 'Sobel', [], 'vertical');
subplot(3, 5, 13);
imshow(Gx_new2);
title('Grad Gx(New 2)');
subplot(3, 5, 14);
imshow(Gy_new2);
title('Grad Gy(New 2)');
G_new2 = sqrt(double(Gx_new2).^2 + double(Gy_new2).^2);
G_new2 = uint8(G_new2 * (255 / max(G_new2(:))));
subplot(3, 5, 15);
imshow(G_new2);
title('Grad Gx + Gy(New 2)');

sgtitle('Edge Detection Results using Sobel Operator', 'FontSize', 14);
```
<img width="1874" height="793" alt="image" src="https://github.com/user-attachments/assets/a8c2c987-ac24-4998-b108-ed4fa5efbab7" />

---
## 🧩 Operator Comparison

| Operator    | Edge Sharpness | Noise Sensitivity | Ideal Use                  |
| ----------- | -------------- | ----------------- | -------------------------- |
| **Prewitt** | Medium         | Low               | General edge detection     |
| **Roberts** | High           | High              | Fine edges & small details |
| **Sobel**   | Strong         | Medium            | Clear object boundaries    |

---




Would you like me to make a **GitHub folder structure suggestion** (like `/images`, `/docs`, `/matlab_codes`, `/results`) and add links inside the README for neat organization?
```
