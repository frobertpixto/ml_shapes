# Shape Dataset

## Summary
Dataset of Hand Drawn Images of shapes. 
![examples](readme_images/train_images.png)

## Directory Structure
- **data**: Contains all the Dataset, with Images and Vertices .
  - 1 directory per user
    - For each sample, there is:
      - A file with an image like: images/ellipse/*ellipse.aly.0001*.png
      - A file with the vertices coordinates, like: vertices/ellipse/*ellipse.aly.0001*.csv
- **processing**: Contains notebooks for ETL and modelisation.
  - **classify**: Classification
  - **find_vertices**: Regression

## Dataset
- a Dataset of Shapes and Vertices for Machine Learning **Classification** and **Regression**.  

I have created this Dataset for my app **[Mix on Pix](https://apps.apple.com/us/app/mix-on-pix-text-on-photos/id633281586)**.

## The Images 
Images exist in 4 shapes:
- Ellipse
- Rectangle
- Triangle
- Other

The Dataset contains images (70px x 70 px x 1 gray channel) distributed as:

| Total | Other | Ellipse |  Rectangle | Triangle |
| :---------------:|---------------:|---------------:|---------------:|---------------: |
| **27292** images  |  7287  | 6454 |  6956  | 6595 |

## Processing
### Classification
Hand Drawn Images of shapes are classified to determine the type of each shape.   
More details [here](processing/classify/README.md).
### Regression  
Regression is used to determine the exact **intended size and angle** of each drawn shape.  
The vertices are the oranges points superimposed on the ellipses in the examples below.   

![examples](readme_images/vertices_ell.png)

More details [here](processing/find_vertices/README.md).


## The Data
### People
Images were mostly generated by asking people I knew to draw Ellipses, Rectangles and Triangles in [Mix on Pix](https://apps.apple.com/us/app/mix-on-pix-text-on-photos/id633281586).  
People were aged from 7 to 87. I asked them to draw the way they wanted, slow or fast. In particular, I did not ask to draw nice shape. It was the **intent** while drawing that interested me.
### Tools
- I have created tools within [Mix on Pix](https://apps.apple.com/us/app/mix-on-pix-text-on-photos/id633281586) to generate 70px x 70px png files for each shape drawn.  
- I also created tools in [Mix on Pix](https://apps.apple.com/us/app/mix-on-pix-text-on-photos/id633281586) to position the Vertices.

I then used these images to train models that are used in [Mix on Pix](https://apps.apple.com/us/app/mix-on-pix-text-on-photos/id633281586) Auto-Shapes feature.
### Shape of type Other
The first ML model had no **Other** shape. I was initially happy with the excellent accuracy when the drawing corresponded to the intent. But when testing internally with [Mix on Pix](https://apps.apple.com/us/app/mix-on-pix-text-on-photos/id633281586), bad  drawings would always be recognized as one of Ellipse, Rectangle or Triangle. It is not a great user experience.    
Moreover, when attacking the more difficult problem of determining the vertices of a shape, the distinction of **Other** shapes became important.


---
# To do
## General
- Specify Licence for Data and for Notebooks
- Write about Hyperparameters and tweaks (like reference for first point for vertices).
- Create a DataSheet for the Dataset as described in https://arxiv.org/pdf/1803.09010.pdf  

## Vertices
- Finalize Ellipses
- Indicate the difficulties, hyper-parameters adjustments and tweaks.
  - Augmentation in general
    - First point in particular
- Show video of classification and finding vertices in actions.    

## Later if requested
- Explain pipeline
- Add requirements.txt for Notebooks
- Show model to calculate Vertices for Rectangles and Triangles

---
by Francois Robert 

