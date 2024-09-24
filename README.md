# Morphological_imaging
image_morphing_using_matlab

inputImage = imread('your_image.png');
figure;
imshow(inputImage);
title('Original Image');

seDisk = strel('disk', 5); % Disk structuring element with radius 5

dilatedImage = imdilate(inputImage, seDisk);
figure;
imshow(dilatedImage);
title('Dilated Image');

erodedImage = imerode(inputImage, seDisk);
figure;
imshow(erodedImage);
title('Eroded Image');

openedImage = imopen(inputImage, seDisk);
figure;
imshow(openedImage);
title('Opened Image');

closedImage = imclose(inputImage, seDisk);
figure;
imshow(closedImage);
title('Closed Image');

gradientImage = imsubtract(dilatedImage, erodedImage);
figure;
imshow(gradientImage);
title('Morphological Gradient');

tophatImage = imtophat(inputImage, seDisk);
figure;
imshow(tophatImage);
title('Top-hat Image');

bottomhatImage = imbothat(inputImage, seDisk);
figure;
imshow(bottomhatImage);
title('Bottom-hat Image');
