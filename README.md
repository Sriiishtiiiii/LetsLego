# LetsLegoIt
This project implements a "legofication" effect on images using Python and several key libraries.  The process involves image compression, upscaling, and the application of a Lego-like pattern.

**Technologies Used:**

* **Python:** The core programming language for the project.
* **NumPy:**  Used for numerical operations, especially for array manipulation essential for image processing.
* **Matplotlib:**  Used for displaying the image results, including adjusting figure size and turning off axes.
* **OpenCV (cv2):**  Leveraged for image resizing (compression and upscaling) operations, utilizing different interpolation methods for quality control.
* **Scikit-image (skimage):**  Employed for image input/output (reading the image) and for creating the circular disk shapes characteristic of the Lego brick pattern.


**Workflow:**

1. **Image Input:** The script begins by reading an image (presumably `Mona_Lisa.jpg` from the local directory) using scikit-image's `io.imread()`.

2. **Compression:** The image is downscaled using OpenCV's `cv.resize()` function with `cv.INTER_AREA` interpolation.  The level of compression is controlled by the `NPIXEL` parameter, which affects the final size of the compressed image.

3. **Upscaling:**  The compressed image is then upscaled using `cv.resize()` again, but this time with `cv.INTER_NEAREST` interpolation to create a pixelated effect.  The `factor` parameter controls the target size of the upscaled image.

4. **Legofication:** This is the core image manipulation step. It iterates through a grid defined by `nblocks` (derived from the shape of the compressed image), placing colored circles simulating Lego bricks on the upscaled image.  The color of each simulated brick is determined by the pixel color at the center of the brick's location in the original compressed image. Key functions from scikit-image's `draw` module are used for drawing the disks.  The process is designed to mimic the appearance of a Lego mosaic.

5. **Display:** Finally, the resulting "legofied" image is displayed using Matplotlib.
