Model Training in Colab: 
https://colab.research.google.com/drive/1dIbm6Ld0lTjNXL67gQj5yiMSF4YMX_ye?usp=sharing

# Deploying locally [Refference: https://github.com/EdjeElectronics/Train-and-Deploy-YOLO-Models]
1. Unzip <my_model.zip> 
2. Create python env:
    conda create --name yolo-env1 python=3.12 -y
    conda activate yolo-env1
3. Install requirements:
    pip install ultralytics
    Install Nvidia GPU-enabled version of PyTorch by issuing the following command:
        pip install --upgrade torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
4. Locate the file: cd my_model
5. Clone detection utils file created by Evan Juras, EJ Technology Consultants. Add coordinates extraction function. 
curl -o yolo_detect.py https://raw.githubusercontent.com/EdjeElectronics/Train-and-Deploy-YOLO-Models/refs/heads/main/yolo_detect.py
6. Detect objects in video: 
python yolo_detect.py --model my_model.pt --source ../sample.mp4 --resolution 640x640 --coordinates True
