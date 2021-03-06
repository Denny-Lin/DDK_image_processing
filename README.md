# DDK_image_processing
This repo will show something for image processing. 
* Just try and learn by myself.
* Read an image. 
* Do OCR or ...
  * Pre-processing
  * Text recognition
  * Post-processing
  * Application-specific optimizations 
* Output a new file/image.
* ...
## Prepare a \*.bmp image
* Just google a picture and download it.
* Use windows paint to open it and save as 24-bit bmp. <br>
![124](https://user-images.githubusercontent.com/67073582/126836896-163f646c-f2c7-4b01-bd1a-f72da52e4cef.png) <br>
* We can use structures from #include<windows.h> or create a structure follow this image.
* BITMAPINFOHEADER head;
* // size_t fread(void *ptr, size_t size, size_t nmemb, FILE *stream)
* fread(&head, sizeof(BITMAPINFOHEADER), 1, fp);
* I found a concept and code online and that's a simple code, so we should modify it.
* for example, it should be strcut or namespce{class{function(){}}}.
* Although I am busy recently, I still keep going for this project.

## What will I do?
* First, choose a basic type of a image.
* We should focus on OCR, not the decode/encode of a image.
* Set the fixed buffer to eliminate the times of copy & paste between the user and kernel space.
* Think about what the functions should be created? 
* I think we should change the original image to black & white image below: <br>
![image](https://user-images.githubusercontent.com/67073582/124179100-e38d0280-dae4-11eb-8fc4-b53b04bccd0b.png) <br>
* let's think of the algorithm here.
* greyscale <br>
![image](https://user-images.githubusercontent.com/67073582/124598538-50165180-de97-11eb-9b64-0772149a21b6.png) <br>
![image](https://user-images.githubusercontent.com/67073582/124650637-83bf9e80-decc-11eb-9948-0cfd599d647e.png) <br>
* The first idea coming to mind is choosing the middle tone color, but that's wrong. 
* Just think if all the pixels are on the right or left side of the middle tone color .
* So can we count all the pixels and find a peak of pixel to be the threshold?, such as this image below: <br>
![image](https://user-images.githubusercontent.com/67073582/124599950-d0898200-de98-11eb-81f0-df71f5a52a54.png) <br>
* It still have a problem that same degree of pixels can get together in different place of a image, it means two peaks or more.
* ... <br>
* Image Denoising - Looks like if just a white point in black, we should change this white point to a black point.
![image](https://user-images.githubusercontent.com/67073582/124179799-e3413700-dae5-11eb-91dc-8e9242279b8a.png)
* ...


## What can we have if we finish this project?
* We can have our own library "DDK_CV".
* Do AI.
* ...

## References
* https://homepages.inf.ed.ac.uk/rbf/BOOKS/PHILLIPS/cips2ed.pdf
* https://en.wikipedia.org/wiki/Optical_character_recognition
* https://en.wikipedia.org/wiki/Thresholding_(image_processing)
* https://en.wikipedia.org/wiki/Grayscale
* https://gist.github.com/t1ina2003/6851912
* https://gist.github.com/FourMiao/5386494
* https://blog.csdn.net/fengxianghui01/article/details/85076319
* https://www.jinnsblog.com/2009/08/bmp-format-graphic-illustration.html
* ... 
