# exploradome_tangram
Tangram form detection from live video stream in the real time. 
We use intermediate stages crop, contrast

In order to run this annotation tool, run 'main.py' file.

## Installation and Usage

OpenCV (Open Computer Vision Library) 
Numpy 
Imutils  

```python
pip install opencv-python
pip install numpy
pip install imutils
```
## How To Use


<<<<<<< HEAD
```shell
git clone https://github.com/Nohossat/exploradome_tangram/tree/numpy---team-4
cd exploradome_tangram
python -m venv venv/
source venv/Scripts/activate
pip install -r requirements.txt

# launch the app with an external webcam on the right side of the board
python3 main.py --mode 1 --side right

# launch the app with a video on the left side
python3 main.py --mode /videos/coeur.pm4 --side left

# launch the app with an image on the right side
python3 main.py --mode /videos/coeur.jpg --side right
```

## Approach
=======
# Approach
>>>>>>> 4736ba6286ede05cc13cb1d684fbdd976e5f56a7
Find the best accuracy for the model 
Calculation distances geometrics by analyse of contours
Keywords : Hu Moments, moments, distances

![metric..jpg](:storage\3b3b020d-451d-4214-ae57-e99804810a72\fdf77c5e.jpg)

## Configuration
Data 
- tangrams - image classification datasets (from video_to_img)
- hu_moments.csv
- moments
Tests 
- tests unitaire
App.py 
- main entry in the application: tangram_game 
distances.py 
- calcul the distances between of humoments
find_corner.py
- calcul of corners every image
metrics.py
- from a set of images, get global accuracy, precision, recall
moments.py
- this function returns the shape's Moments or Hu Moments
- compare moments of a frame with the hu moments of our dataset images
- print the probabilities to belong to each class in descending order (Pandas DataFrame)
prepare_tangrams_dataset.py
- compute moments / hu moments for all images in our dataset
processing.py
- this function takes a cv image as input, calls the resize function, crops the image to keep only the board, chooses the left / right half of the board or the full board if the child is playing alone, and eventually finds the largest dark shape
## Resultat
Two objectives:
- detect one or two tangrams at the same time, in real time, having twelve different shapes
- detect the parts of the tangram (triangle, square etc.)

## Testing the metrics
The code is tested with Pytest
### Unit Tests

We test each function individually

### Integration Tests

Dynamic tests

#### Static tests
We compare every image with our dataset. We need several images by class.

#### Video tests
We compare a video with our dataset. We need different sequences with a clear solution
