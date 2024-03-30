# Running ComfyUI with AMD + ZLUDA (Windows)

## Requirements:
- ZLUDA (Installed and PATH enabled)
- Git
- Miniconda

1. Download and install Miniconda from [here](https://docs.anaconda.com/free/miniconda/index.html).

2. Open the Anaconda Prompt (miniconda3) terminal.

3. Create a new directory where you want to save your files.

4. Navigate to the directory and execute the following command: 
    ```bash
    conda create -n comfyui python=3.10.8 -y
    ```

5. Activate the environment:
    ```bash
    conda activate comfyui
    ```

6. Change directory to `ComfyUI`:
    ```bash
    cd .\ComfyUI\
    ```

7. Create a virtual environment:
    ```bash
    python -m venv venv
    ```

8. Activate the virtual environment:
    ```bash
    .\venv\Scripts\activate
    ```

9. Install the required packages:
    ```bash
    .\venv\Scripts\python.exe -m pip install -r .\requirements.txt
    ```

10. Install Torch and Torchvision:
    ```bash
    pip install torch==2.2.0 torchvision --index-url https://download.pytorch.org/whl/cu118
    ```

11. Navigate to `venv\Lib\site-packages\torch\lib`


12. Copy `cublas64_11.dll` and `cusparse64_11.dll` from ZLUDA (`cublas.dll` and `cusparse.dll` respectively) and paste them here.


13. *** IMPORTANT *** Before running ComfyUI, you must apply the following changes in `model_management.py` and `cuda_malloc.py`. Both files are located in `ComfyUI\comfy`:
    * [model_management.py](https://github.com/zubenelakrab/ComfyUI_AMD_ZLUDA/commit/9ade8ca17156c7e18949f07180c1aee976b1d0d6)
    * [cuda_malloc.py](https://github.com/zubenelakrab/ComfyUI_AMD_ZLUDA/commit/b3b993d194bdbdd67c1178a95f1fe823e13b7ff6)
          
14. Run the main script:
    ```bash
    python .\main.py
    ```

Now, ComfyUI should be up and running using AMD with ZLUDA on Windows.

