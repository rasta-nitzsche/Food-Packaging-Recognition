# Food-Packaging-Recognition

This project involves acquiring images of packaging for food products, for example: bags of snacks, breakfasts, box of spaghetti, salad bag, tin can. And then, we must, by an application, identifying the following items on such packaging:

- text boxes (for example: the list of ingredients)
- specific marking areas (barcode, QR code)
- areas of graphic elements (Logo, characters (for example, the bear on the jar of peanut butter, etc.)

![alt text](https://github.com/rasta-nitzsche/Food-Packaging-Recognition/blob/main/test_batch0_labels.jpg)

Our solution was to design an architecture composed of two modules: a module for the recognition of different areas (product-recognition), and a module for converting images into text (OCR or Optical Character recognition), we follow up the link between these two modules to obtain a functional pipeline.
