# Ejecutar ComfyUI con AMD + ZLUDA (Windows)

## Requisitos:
- ZLUDA (Instalado y habilitado en el PATH)
- Git
- Miniconda

1. Descarga e instala Miniconda desde [aquí](https://docs.anaconda.com/free/miniconda/index.html).

2. Abre el terminal Anaconda Prompt (miniconda3).

3. Crea un nuevo directorio donde desees guardar tus archivos.

4. Navega hasta el directorio y ejecuta el siguiente comando:
    ```bash
    conda create -n comfyui python=3.10.8 -y
    ```

5. Activa el entorno:
    ```bash
    conda activate comfyui
    ```

6. Cambia al directorio `ComfyUI`:
    ```bash
    cd .\ComfyUI\
    ```

7. Crea un entorno virtual:
    ```bash
    python -m venv venv
    ```

8. Activa el entorno virtual:
    ```bash
    .\venv\Scripts\activate
    ```

9. Instala los paquetes necesarios:
    ```bash
    .\venv\Scripts\python.exe -m pip install -r .\requirements.txt
    ```

10. Instala Torch y Torchvision:
    ```bash
    pip install torch==2.2.0 torchvision --index-url https://download.pytorch.org/whl/cu118
    ```

11. Navega hasta `venv\Lib\site-packages\torch\lib`

12. Copia `cublas64_11.dll` y `cusparse64_11.dll` de ZLUDA (`cublas.dll` y `cusparse.dll` respectivamente) y pégalos aquí.

13. Ejecuta el script principal:
    ```bash
    python .\main.py
    ```

Ahora, ComfyUI debería estar funcionando con AMD y ZLUDA en Windows.
