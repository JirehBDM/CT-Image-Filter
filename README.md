# CT-Image-Filter
A script to add low pass, high pass, and edge detection filters to a CT scan to assist in image reading and diagnosis.

## Language
- Matlab
## Features
- Displays the original image
- Displays the image under a highpass filter
- Displays the image under a lowpass filter
- Displays the image under an edge detection filter.
 
## The Input

The provided file *LungCT.tif* contains the image of a lung obtained from a CT scan.

## The Process

First, the image needs to be read and interpreted by the program. Using the ```imread``` command, MatLab interprets this image as an array of numerical values, with each value defining the properties of a pixel. The array is stored within the variable ‘Lungpic’.

MatLab interpreting the image this way allows it to be edited in a simplified manner. By simply editing the values in the array, the properties of each pixel can be visually changed. The visual change is usually represented in a change of “brightness”, brightening the image with a high pass filter can remove or conceal image grain/noise. Furthermore, the image can be sharpened by  reducing the focus on the edges of the image to emphasize the center with a low pass filter. Two filter arrays are made with values representing just that and are stored as ‘lowpass_filter’ and ‘highpass_filter’ respectively.

Onec the filters have been made, they can be applied or “Convoluted” onto the image. The filter is applied using the ```conv2``` command. This command *merges* the values of 2 matrices together, and in the case where the matrices’ sizes greatly differ from each other, the output will take the size of the larger matrix. The values of the smaller matrix will be smoothed evenly across the values of the larger matrix. This makes it a great command to use when working with images. The highpass and lowpass filters are applied to the image using this command.

The edges of the image are defined by convoluting the image with the edge detecting matrices. Once the edges for each axis are defined, the edges can be combined
using the formula of magnitude.

The images can be organized using the subplot command, and while using the ‘image’ command, any array can be displayed as an image that is defined by the numerical values of its contents. Hence it is used to display the original alongside its filtered images.

The ```colormap(gray(…))``` command is used the change the contrast of the image to improve visibility by mapping the color of the image in gray, and tweaking its saturation with the numbers within the command.

## The output

<img width="534" height="404" alt="image MJIYM3" src="https://github.com/user-attachments/assets/ef70fddc-1721-408f-b14f-ed7db35ddd7e" />

The results of the code show 4 images with distinct properties. The original can be seen, along with its sharper and smoother counterparts.

These filters helped improve the image reading by removing noise, highlighting edges, and making important features like tumors easier to see.
The filters can make it easier to spot differences between healthy and unhealthy tissues. This work shows how useful image filtering is in medical imaging and how it can help with better analysis and cancer research.

## What I learned

### MatLabs Image reading:
-  Working on this project made it clearer to me about how MatLab processes and reads images. They can be read as number arrays, which makes it compatible in use with most other MatLab commands that arent specically for image processing.
### Image related commands:
-  This project expanded my knowlege on the more niche MatLab commands used for processing images, I had to learn how to use the ```conv2```, and it's clear that I may be seeing more of this in my future projects and work.
### Use of Image Filters
-  I found out how useful image filters are in the medical field. Though the filter I worked on here was quite simple, filters in general can be used in highlighting and spotting differences between healthy and unhealthy tissue.


### Overall Growth:
Each part of this project helped me understand more about coding in Matlab, image processing, and improving clinical experience. It was more than just making a tool, it was about solving problems, learning new things, and improving my skills for future projects and work.

## How It Can Be Improved
-  The filter arrays could be made larger than 3x3, to provide more precise filtering.
-  The values could be adjusted to provide less grain in the final images.

## License
-  This project was completed for academic purposes and is open for educational use.
