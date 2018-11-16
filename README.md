# **Finding Lane Lines on the Road**
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

The goals of this project was to make a pipeline that finds lane lines on the road and to reflect on my work in a written report.

[image0_origin]: ./test_images/solidWhiteCurve.jpg "solidWhiteCurve, original"
[image1_origin]: ./test_images/solidWhiteRight.jpg "solidWhiteRight, original"
[image2_origin]: ./test_images/solidYellowCurve.jpg "solidYellowCurve, original"
[image3_origin]: ./test_images/solidYellowCurve2.jpg "solidYellowCurve2, original"
[image4_origin]: ./test_images/solidYellowLeft.jpg "solidYellowLeft, original"
[image5_origin]: ./test_images/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, original"

[image0_mask_wy]: ./test_images_output/00_mask_white_yellow/solidWhiteCurve.jpg "solidWhiteCurve, white & yellow masking"
[image1_mask_wy]: ./test_images_output/00_mask_white_yellow/solidWhiteRight.jpg "solidWhiteRight, white & yellow masking"
[image2_mask_wy]: ./test_images_output/00_mask_white_yellow/solidYellowCurve.jpg "solidYellowCurve, white & yellow masking"
[image3_mask_wy]: ./test_images_output/00_mask_white_yellow/solidYellowCurve2.jpg "solidYellowCurve2, white & yellow masking"
[image4_mask_wy]: ./test_images_output/00_mask_white_yellow/solidYellowLeft.jpg "solidYellowLeft, white & yellow masking"
[image5_mask_wy]: ./test_images_output/00_mask_white_yellow/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, white & yellow masking"

[image0_gray]: ./test_images_output/01_grayscale/solidWhiteCurve.jpg "solidWhiteCurve, grayscale"
[image1_gray]: ./test_images_output/01_grayscale/solidWhiteRight.jpg "solidWhiteRight, grayscale"
[image2_gray]: ./test_images_output/01_grayscale/solidYellowCurve.jpg "solidYellowCurve, grayscale"
[image3_gray]: ./test_images_output/01_grayscale/solidYellowCurve2.jpg "solidYellowCurve2, grayscale"
[image4_gray]: ./test_images_output/01_grayscale/solidYellowLeft.jpg "solidYellowLeft, grayscale"
[image5_gray]: ./test_images_output/01_grayscale/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, grayscale"

[image0_gauss]: ./test_images_output/02_gaussian_smoothing/solidWhiteCurve.jpg "solidWhiteCurve, gaussian smoothing"
[image1_gauss]: ./test_images_output/02_gaussian_smoothing/solidWhiteRight.jpg "solidWhiteRight, gaussian smoothing"
[image2_gauss]: ./test_images_output/02_gaussian_smoothing/solidYellowCurve.jpg "solidYellowCurve, gaussian smoothing"
[image3_gauss]: ./test_images_output/02_gaussian_smoothing/solidYellowCurve2.jpg "solidYellowCurve2, gaussian smoothing"
[image4_gauss]: ./test_images_output/02_gaussian_smoothing/solidYellowLeft.jpg "solidYellowLeft, gaussian smoothing"
[image5_gauss]: ./test_images_output/02_gaussian_smoothing/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, gaussian smoothing"

[image0_canny]: ./test_images_output/03_canny_edge_detection/solidWhiteCurve.jpg "solidWhiteCurve, canny edge detection"
[image1_canny]: ./test_images_output/03_canny_edge_detection/solidWhiteRight.jpg "solidWhiteRight, canny edge detection"
[image2_canny]: ./test_images_output/03_canny_edge_detection/solidYellowCurve.jpg "solidYellowCurve, canny edge detection"
[image3_canny]: ./test_images_output/03_canny_edge_detection/solidYellowCurve2.jpg "solidYellowCurve2, canny edge detection"
[image4_canny]: ./test_images_output/03_canny_edge_detection/solidYellowLeft.jpg "solidYellowLeft, canny edge detection"
[image5_canny]: ./test_images_output/03_canny_edge_detection/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, canny edge detection"

[image0_mask_fl]: ./test_images_output/04_mask_front_lane/solidWhiteCurve.jpg "solidWhiteCurve, front lane masking"
[image1_mask_fl]: ./test_images_output/04_mask_front_lane/solidWhiteRight.jpg "solidWhiteRight, front lane masking"
[image2_mask_fl]: ./test_images_output/04_mask_front_lane/solidYellowCurve.jpg "solidYellowCurve, front lane masking"
[image3_mask_fl]: ./test_images_output/04_mask_front_lane/solidYellowCurve2.jpg "solidYellowCurve2, front lane masking"
[image4_mask_fl]: ./test_images_output/04_mask_front_lane/solidYellowLeft.jpg "solidYellowLeft, front lane masking"
[image5_mask_fl]: ./test_images_output/04_mask_front_lane/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, front lane masking"

[image0_hough]: ./test_images_output/05_hough_transform/solidWhiteCurve.jpg "solidWhiteCurve, hough transform"
[image1_hough]: ./test_images_output/05_hough_transform/solidWhiteRight.jpg "solidWhiteRight, hough transform"
[image2_hough]: ./test_images_output/05_hough_transform/solidYellowCurve.jpg "solidYellowCurve, hough transform"
[image3_hough]: ./test_images_output/05_hough_transform/solidYellowCurve2.jpg "solidYellowCurve2, hough transform"
[image4_hough]: ./test_images_output/05_hough_transform/solidYellowLeft.jpg "solidYellowLeft, hough transform"
[image5_hough]: ./test_images_output/05_hough_transform/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, hough transform"

[image0_weight]: ./test_images_output/06_weighted/solidWhiteCurve.jpg "solidWhiteCurve, lines overlayed"
[image1_weight]: ./test_images_output/06_weighted/solidWhiteRight.jpg "solidWhiteRight, lines overlayed"
[image2_weight]: ./test_images_output/06_weighted/solidYellowCurve.jpg "solidYellowCurve, lines overlayed"
[image3_weight]: ./test_images_output/06_weighted/solidYellowCurve2.jpg "solidYellowCurve2, lines overlayed"
[image4_weight]: ./test_images_output/06_weighted/solidYellowLeft.jpg "solidYellowLeft, lines overlayed"
[image5_weight]: ./test_images_output/06_weighted/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch, lines overlayed"

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps:
1. Masking of yellow and white colors. I did experiment with HSV, HSL and RGB colorspaces, however RGB masking seemed sufficient enough for further processing.
    Below is the function used to apply color masks, complete with thresholds defining the color ranges.
    
```python
def apply_color_masks(image):
    """Applies white and yellow colors masks"""

    mask_white = cv2.inRange(image, np.array([90, 90, 200]), np.array([255, 255, 255]))
    mask_yellow = cv2.inRange(image, np.array([215, 170, 0]), np.array([255, 255, 180]))
    mask_combined = cv2.bitwise_or(mask_white, mask_yellow)
    return cv2.bitwise_and(image, image, mask = mask_combined)
```
Original | White&yellow masking
:---:|:---:
![][image0_origin] | ![][image0_mask_wy]

2. Convertion of a masked image to grayscale colorspace as it is required in Canny Edge Detection step.

White&yellow masking | Grayscaled
:---:|:---:
![][image0_mask_wy] | ![][image0_gray]

3. Gaussian smoothing to prevent false detection caused by noise. This filter is built into Canny Edge Detection algorithm, however separating it as another step makes the filter more flexible.

Grayscaled | Gaussian smoothing
:---:|:---:
![][image0_gray] | ![][image0_gauss]

4. Applying Canny Edge Detection.

Gaussian smoothing | Canny edge detection
:---:|:---:
![][image0_gauss] | ![][image0_canny]

5. Masking of a front lane ahead of the car, so only this area would be processed in further steps.

Canny edge detection | Front lane masking
:---:|:---:
![][image0_canny] | ![][image0_mask_fl]

6. Applying Hough transform to easily aggregate and draw lane lines.

Front lane masking | Hough transform
:---:|:---:
![][image0_mask_fl] | ![][image0_hough]

7. Final step of overlaying the lines onto original image.

Hough transform | Overlaying
:---:|:---:
![][image0_hough] | ![][image0_weight]


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by incorporating basic line equations. For every line the slope, y-interception and length are being calculated. Slope of the line is used to make a distinction between left or right lane line. Y-axis goes from top-to-bottom of the image so negative slope results in left lane line.
```python
if line_slope < 0:
    if not l_lines.size:
        l_lines = np.array([[line_slope, line_y_intercept, line_length]])
    l_lines = np.concatenate((l_lines, [[line_slope, line_y_intercept, line_length]]), axis = 0)
else:
    if not r_lines.size:
        r_lines = np.array([[line_slope, line_y_intercept, line_length]])
    r_lines = np.concatenate((r_lines, [[line_slope, line_y_intercept, line_length]]), axis = 0)
```
Next step is to calculated the weighted average of all slopes and all y_intercepts, with weights being line lengths.
```python
wavg_l_slope = np.average(l_lines[:,0], weights=l_lines[:,2])
wavg_l_y_intercept = np.average(l_lines[:,1], weights=l_lines[:,2])
```
Once we have those parameters averaged we can calculate x cooridinates of the points creating the line. We assume y_0 is the bottom of the image (full height) and y_1 is around y_1 = 0.65 * y_0 (at y_1 < 0.6 * y_0 lane lines cross each other).
```python
l_x1 = np.int_((y1 - wavg_l_y_intercept) / wavg_l_slope)
l_x2 = np.int_((y2 - wavg_l_y_intercept) / wavg_l_slope)
cv2.line(img, (l_x1, np.int_(y1)), (l_x2, np.int_(y2)), color, thickness)
```
Once we have line coordinates all we have to do is to draw the lines onte the original image.

Below is the process of Lane Lines Detection for all images from test_images directory.

Original | White&yellow masking | Grayscaled | Gaussian smoothing | Canny edge detection | Front lane masking | Hough transform | Overlaying
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
![][image0_origin] | ![][image0_mask_wy] | ![][image0_gray] | ![][image0_gauss] | ![][image0_canny] | ![][image0_mask_fl] | ![][image0_hough] | ![][image0_weight]
![][image1_origin] | ![][image1_mask_wy] | ![][image1_gray] | ![][image1_gauss] | ![][image1_canny] | ![][image1_mask_fl] | ![][image1_hough] | ![][image1_weight]
![][image2_origin] | ![][image2_mask_wy] | ![][image2_gray] | ![][image2_gauss] | ![][image2_canny] | ![][image2_mask_fl] | ![][image2_hough] | ![][image2_weight]
![][image3_origin] | ![][image3_mask_wy] | ![][image3_gray] | ![][image3_gauss] | ![][image3_canny] | ![][image3_mask_fl] | ![][image3_hough] | ![][image3_weight]
![][image4_origin] | ![][image4_mask_wy] | ![][image4_gray] | ![][image4_gauss] | ![][image4_canny] | ![][image4_mask_fl] | ![][image4_hough] | ![][image4_weight]
![][image5_origin] | ![][image5_mask_wy] | ![][image5_gray] | ![][image5_gauss] | ![][image5_canny] | ![][image5_mask_fl] | ![][image5_hough] | ![][image5_weight]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lines are occasionally not detected at all or are heavily shadowed. Another shortcoming could be detecting the lines from the wrong road surface markings. Another shortcoming could be detecting left line but not detecting the other line.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to narrow down a range of possible line slopes. Another potential improvement could be to keep memory of e.g. last 5 time frames. Then if the line is not detected it could be derived from previous time frame. In case we can detect only one of the line, we can assume the slope of other lane line since lane lines always follow the same direction.
