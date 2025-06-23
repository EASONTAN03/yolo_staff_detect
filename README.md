# Staff Detection
## Model Training in Colab: 
https://colab.research.google.com/drive/1dIbm6Ld0lTjNXL67gQj5yiMSF4YMX_ye?usp=sharing

## Project Organization

```
├── README.md          <- The top-level README for developers using this project.
├── docs               <- Documentations
│   └── Staff_Detect_Report.docx     <- Report of Model.
│   
├── my_model           <- Directory of model, outputs
│   ├── train              <- Model training reports.
│   ├── my_model.pt        <- Best weights 
│   └── yolo_detect.py     <- Detection utils
│ 
└── .gitignore
```

## Deploying locally 
[Refference](https://github.com/EdjeElectronics/Train-and-Deploy-YOLO-Models)

        git clone https://github.com/EASONTAN03/FootfallCam_staff_detect
        
1. Unzip <my_model.zip> 
2. Create python env:

        conda create --name yolo-env1 python=3.12 -y

        conda activate yolo-env1
   
4. Install requirements:
   
        pip install ultralytics
   
    Install Nvidia GPU-enabled version of PyTorch by issuing the following command:

        pip install --upgrade torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
   
6. Locate the file: ```cd my_model```
7. Modify detection utils file created by Evan Juras, EJ Technology Consultants. [yolo_detect.py]
- Add coordinates extraction function. 
- Add bouding box comparison for staff detection: if box of staff_tag is inside box of staff then staff detected.
8. Detect objects for video:
  
        python yolo_detect.py --model my_model.pt --source ../sample.mp4 --resolution 640x640 --coordinates True


## Demo of running the detection
[Demo_staff_detect](https://www.youtube.com/watch?v=6_Xb9QUhnJ8)
