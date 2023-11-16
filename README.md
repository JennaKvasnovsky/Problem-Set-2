# Problem-Set-2
# Image Processing with OpenCV and Filters

## Introduction

This code demonstrates basic image processing tasks using OpenCV and explores the application of convolution filters to create feature maps.

## Section 1: Load RGB Image

Load an RGB image from a URL using OpenCV.

```python
url = "https://upload.wikimedia.org/wikipedia/commons/4/47/PNG_transparency_demonstration_1.png"
response = requests.get(url)

try:
    # Load and convert the image
    img_array = np.asarray(bytearray(response.content), dtype="uint8")
    img = cv2.imdecode(img_array, cv2.IMREAD_COLOR)
    img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

except Exception as e:
    print(f"Error: {e}")

## Section 2: Display the Original Image

Display the loaded image using Matplotlib.

```python
plt.imshow(img)
plt.title("Original Image")
plt.show()
```

## Section 3: Display the Image in Colab (if applicable)

Display the image using OpenCV in Colab.

```python
try:
    from google.colab.patches import cv2_imshow
    cv2_imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
except Exception as e:
    print(f"Error: {e}")
```

## Section 4: Plot a Line along a Specific Row

Plot a line along a specific row in the image.

```python
row_to_plot = 100
row_values = np.mean(img[row_to_plot, :], axis=1)

plt.plot(row_values, label=f'Row {row_to_plot}')
plt.title("Line Plot of Image")
plt.xlabel("Column")
plt.ylabel("Pixel Value")
plt.legend()
plt.show()
```

... (Continue with the remaining sections)

---

## Link to Colab Notebook
[[OpenCV_Image_Processing.ipynb](link-to-your-colab-notebook)](https://github.com/JennaKvasnovsky/Problem-Set-2/blob/main/PROBLEM_2.ipynb)

## Conclusion

This code provides a step-by-step demonstration of loading, processing, and visualizing images using OpenCV in Python. The application of convolution filters enhances the understanding of feature extraction in image processing.
