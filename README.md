# URI_CapstoneProject


# DATA SET - PROPERTIES

The Car Detection data set is a sequence of still captures (frames) of cars driving through a section of road.
Every frame is stored in a JPG and has a correspoding TXT file with the coordinates of the “bounding box”
for each car detected in frame. Each line represents a car with the coordinates seprated by a space:

	<class_id> <x_center> <y_center> <width> <height>

where class_id of 0 represents a car object.  If there were multiple object types, different numbers would represent different classes.
This system of encoding represents the YOLO label format (normalized).

Unlike pixel-based bounding boxes, YOLO uses values between 0 and 1, meaning:
	x_center = 0.5 means the box is centered in the middle of the image.
	width = 1.0 would mean the box spans the entire image width.


