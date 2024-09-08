# bpyscripts
## Rendering
### Render object from all angles
An update of dr.Sybren's "Rendering from 'all' angles" script from the Scripting for Artists video series for Blender 2.8+ with additional features.
## Video Editing
### Batch-edit text strips
Change all attributes of every text strip in a given track (useful for batch-editing video subtitles). 
## Shading and Texturing
### Color palette from 2D image
Apply the colors of a 2D image to the materials of a 3D object.

#### HSL method for complex images with many colors
The pixels of a small image are converted to HSV color space for grouping according to hue. The HSV values are averaged for each hue group. Hue groups with above average S or V values see those values boosted, and vice versa.
<img alt="Example 1" src="https://github.com/user-attachments/assets/1fbb87aa-edc5-475d-b092-e241a89ffb52" width="49.5%">
<img alt="Example 2" src="https://github.com/user-attachments/assets/2803da71-18dc-494c-9202-9f35ce5353bc" width="49.5%">
<img alt="Example 3" src="https://github.com/user-attachments/assets/7ee70e3c-cd9f-4f9c-b05c-6e21de1ac620" width="49.5%">
<img alt="Example 4" src="https://github.com/user-attachments/assets/7de73726-0180-454c-8f97-db11af7c4161" width="49.5%">

#### RGB method for simple images with few colors
Only the first instance of each color group is taken into account in this simpler method with no color space conversions. 
<img alt="Example 1" src="https://github.com/user-attachments/assets/46cb9013-9938-4503-a02c-f9ad2a488836" width="49.5%">
<img alt="Example 2" src="https://github.com/user-attachments/assets/615a7187-c60d-4bf4-9d05-b156d9ce3bd6" width="49.5%">

<img alt="Example 3" src="https://github.com/user-attachments/assets/45d7d395-e204-4cb7-b8b9-5494f509ed58" width="24.5%">
<img alt="Example 4" src="https://github.com/user-attachments/assets/1ba1aba9-866b-4d47-9ef2-6429367d777f" width="24.5%">
<img alt="Example 5" src="https://github.com/user-attachments/assets/dbae187b-c704-43a9-afb6-43ca29029208" width="24.5%">
<img alt="Example 6" src="https://github.com/user-attachments/assets/6bee63ad-e891-4d2b-a50f-ac517a644a3d" width="24.5%">
