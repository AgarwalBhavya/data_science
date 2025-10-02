AI Assignments – Object Detection & 3D Model Generation
Overview
This repository contains two AI/ML assignments:
Assignment 1 – Object Detection & Segmentation
Uses GroundingDINO, Segment Anything (SAM), and CLIPSeg.
Task: Detect objects in images using natural language prompts and segment them accurately.

Assignment 2 – 3D Model Generation
Converts image or text prompts into 3D models (.obj / .stl).
Provides basic 3D visualization and export support.

Environment Setup
Recommended: Python 3.10 (some libraries are not stable with 3.12).

Create Virtual Environment
conda create -n ai_assignments python=3.10 -y
conda activate ai_assignments

Install Dependencies
# PyTorch (CPU or GPU as per system)
pip install torch torchvision

# Assignment 1: Object Detection
pip install git+https://github.com/IDEA-Research/GroundingDINO.git
pip install git+https://github.com/facebookresearch/segment-anything.git
pip install git+https://github.com/timojl/clipseg.git

# Assignment 2: 3D Model Generation
pip install numpy trimesh matplotlib opencv-python

Assignment 1 – Object Detection & Segmentation
Steps to Run
1.Place your test images inside data/images/.
2.Run detection + segmentation:
python assignment1_object_detection.py --image data/images/sample.jpg --prompt "a person with a red shirt"
3.Output:
Bounding boxes from GroundingDINO
Segmentation masks from Segment Anything
Fine segmentation refinement with CLIPSeg
4.Expected Result
Input: natural language prompt + image
Output: segmented image with highlighted objects

Assignment 2 – 3D Model Generation
Steps to Run
1.From Image Input
python assignment2_3d_model.py --image data/images/object.jpg --output output/model.obj

2.From Text Prompt
python assignment2_3d_model.py --prompt "a simple cube on a plane" --output output/cube.stl

3.Output:
.obj or .stl 3D model file
Preview window with 3D visualization

Repository Structure
├── assignment1_object_detection.py   # Object detection & segmentation pipeline
├── assignment2_3d_model.py           # 3D model generation pipeline
├── data/
│   ├── images/                       # Input images
│   └── outputs/                      # Results (masks, models, previews)
└── README.md                         # Documentation

Deliverables
Assignment 1: Detected + segmented objects in images
Assignment 2: Exported .obj / .stl models from image or text
