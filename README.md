# Food-Packaging-Recognition

This project involves acquiring images of packaging for food products, for example: bags of snacks, breakfasts, box of spaghetti, salad bag, tin can. And then, we must, by an application, identifying the following items on such packaging:

- text boxes (for example: the list of ingredients)
- specific marking areas (barcode, QR code)
- areas of graphic elements (Logo, characters (for example, the bear on the jar of peanut butter, etc.)

![alt text](https://github.com/rasta-nitzsche/Food-Packaging-Recognition/blob/main/test_batch0_labels.jpg)

Our solution was to design an architecture composed of two modules: a module for the recognition of different areas (product-recognition), and a module for converting images into text (OCR or Optical Character recognition), we follow up the link between these two modules to obtain a functional pipeline.

![alt text](https://github.com/rasta-nitzsche/Food-Packaging-Recognition/blob/main/architecture.PNG)

## Model
After doing several research, we opted for Yolov7. It is the latest and most advanced detection model performance available in the current state of the art, moreover, the chosen implementation is a light version allowing to speed up the execution time. We have therefore initialized the weights of our model with the weights of Yolov7 pre-trained on the ImageNet dataset.

## Dataset and preprocessing
We captured (on the phone, on products from supermarket) then annotated 200 images (50 per person) containing the different targeted areas. The annotation was made with Label Studio and the creation of the final dataset (put in yolo format) and data augmentation with Roboflow.
After several training attempts, the following configuration is the one that allowed to obtain the best results:

- Total number of images (after increase): 342 images (272 for
training, 35 for validation and 35 for testing)
- Preprocessing:
  - Resize images (640*640 pixels)
- Types of increase:
    - Rotation (Horizontal and Vertical)
    - Saturation (between -45 and 45%)
    - Grayscale (about 25%)
    - Crop (crop images: 0-25%)
    - Shear (Horizontal and vertical up to 15°)
- Number of epochs (training loops): 300.
- Batch size: 16.

## Results
For the product recognition module, the performance obtained for this module are very correct. Indeed, we were able to obtain an accuracy of 87% on
the code area (bar and QR), 76% on the text area and 60% for the logos.

![alt text](https://github.com/rasta-nitzsche/Food-Packaging-Recognition/blob/main/Capture.PNG)
