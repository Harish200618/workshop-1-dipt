# DIPT-WORKSHOP-1
## Adding Sunglasses to Your Passport Photo Using OpenCV
## Name : Harish S
## Reg.no : 212224240052
```
# Import libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load the Face Image
faceImage = cv2.imread("photo .png")
plt.imshow(cv2.cvtColor(faceImage, cv2.COLOR_BGR2RGB))
plt.title("Face")
plt.axis("off")
# Load the Sunglass image with Alpha channel
glassPNG = cv2.imread("sunglass.jpeg", cv2.IMREAD_UNCHANGED)
plt.imshow(cv2.cvtColor(glassPNG, cv2.COLOR_BGRA2RGBA))
plt.title("glassPNG")
plt.axis("off")
# Resize the sunglass to fit the face
# Tuned for the uploaded image
glassPNG = cv2.resize(glassPNG, (170, 63), interpolation=cv2.INTER_AREA)
print(glassPNG.shape)
# Separate the Color and alpha channels
glassBGR = glassPNG[:,:,0:3]
glassMask1 = glassPNG[:,:,2]
glassBGR.shape
# Display the images for clarity
plt.figure(figsize=[15,15])
plt.subplot(121);plt.imshow(glassBGR[:,:,::-1]);plt.title('Sunglass Color channels');
plt.subplot(122);plt.imshow(glassMask1,cmap='gray');plt.title('Sunglass Alpha channel');
# Make a copy
#faceWithGlassesNaive = resized_faceImage.copy()
faceWithGlassesNaive = faceImage.copy()

# Replace the eye region with the sunglass image
faceWithGlassesNaive[750:1000,480:1250]=glassBGR

plt.imshow(faceWithGlassesNaive[...,::-1])
glassBGR.shape
```

<img width="565" height="556" alt="image" src="https://github.com/user-attachments/assets/05a5122e-b603-4e53-aeff-be1cb6f4957a" />

<img width="797" height="297" alt="image" src="https://github.com/user-attachments/assets/783a388e-8382-416e-a5c7-f15ed5c865dd" />
<img width="1345" height="276" alt="image" src="https://github.com/user-attachments/assets/c7fddba9-b24f-4ceb-9e73-a68db192ed86" />
<img width="1181" height="567" alt="image" src="https://github.com/user-attachments/assets/d3f6f33f-5097-40e1-b82f-7733eee59cee" />




