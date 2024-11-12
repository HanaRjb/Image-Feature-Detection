

```markdown
# Toy Image Analysis

This repository contains code for analyzing images of toys to detect specific features such as hats, faces, legs, and body prints. The code is written in Python and uses the Pillow library for image processing.

## Features
- Detect if a toy has a hat.
- Detect if a toy has a face.
- Detect if a toy has legs.
- Detect if a toy has body prints.

## Requirements
- Python 3.x
- Pillow library

You can install the required library using pip:
```bash
pip install pillow
```

## Usage

1. Clone the repository:
```bash
git clone https://github.com/USERNAME/Image-Feature-Detection.git
cd Image-Feature-Detection
```

2. Prepare your images and place them in the appropriate directory.

3. Modify the `image_path` and `pixels` variables in the code to point to your images and the pixels of interest.

4. Run the script:
```bash
python script.py
```

## Functions
### `resize_image_with_pixels(image_path, pixels)`
This function resizes and crops the image based on the provided pixel coordinates.

### `search_color_in_image1(image, color)`
This function searches for a specific color in the image to detect if the toy has a hat.

### `search_color_in_image2(image, color)`
This function searches for a specific color in the image to detect if the toy has a face.

### `search_color_in_image5(image, color)`
This function searches for a specific color in the image to detect if the toy has legs.

### `search_color_in_image6(image, color)`
This function searches for a specific color in the image to detect if the toy has body prints.

### `get_pixel_color(image_path, x, y)`
This function retrieves the color of a specific pixel in the image.

## Example
```python
from PIL import Image
import math

def resize_image_with_pixels(image_path, pixels):
    # Open the image
    image = Image.open(image_path)

    # Calculate the min and max coordinates
    x_min = min(pixels, key=lambda p: p[0])[0]
    x_max = max(pixels, key=lambda p: p[0])[0]
    y_min = min(pixels, key=lambda p: p[1])[1]
    y_max = max(pixels, key=lambda p: p[1])[1]

    # Crop the image
    cropped_image = image.crop((x_min, y_min, x_max + 1, y_max + 1))

    # Show the cropped image
    cropped_image.show()

    return cropped_image

# Example usage
image_path = "path/to/your/image.jpg"
pixels = [(x1, y1), (x2, y2), (x3, y3), (x4, y4)]
resize_image_with_pixels(image_path, pixels)
```

## License
This project is licensed under the MIT License - see the LICENSE file for details.


