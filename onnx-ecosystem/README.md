# ONNX Converter Ecosystem Docker Container

## About

This tool enables new users to quickly get started working with model conversions and inference in the ONNX model format.

By following the steps below, you will launch a pre-configured Jupyter Notebook environment and explore starter scripts for model conversion from various machine learning frameworks to the ONNX format, using [ONNX Runtime](https://aka.ms/onnxruntime) for inference.

## Supported Framework -> ONNX conversions
- CoreML
- Keras
- SciKit-Learn
- Tensorflow
- PyTorch
- LightGBM
- CNTK
- MXNet
- Caffe (v1)
- LibSVM (preview)

## Usage

0. Ensure that you have Docker installed, or are using Docker for Linux containers if on Windows.

1. Clone this repository.

2. Navigate to the onnx-docker/onnx-ecosystem folder and build the image.
    - `docker build . -t onnx-ecosystem`

3. Run the Docker container to launch a Jupyter notebook server.
    - `docker run -p 8888:8888 onnx-ecosystem`

4. Run `docker ps` in a separate terminal session to get the container name and verify your container is successfully running.

5. Navigate to the url that the Jupyter Notebook is running on and use the provided token in the console.
    - Should be in the form: `http://127.0.0.1:8888/?token=RANDOMSTRINGHERE`  

6. Either upload a file using the Jupyter Notebook button on the top right, or docker cp the required model files to the container.
    - `docker cp PATH_TO_FILE CONTAINER_ID:/scripts/NAME_OF_FILE`

    You can also copy a whole folder using docker.
    - `docker cp PATH_TO_FOLDER/. CONTAINER_ID:/NAME_OF_FOLDER`

7. Navigate to the `converter_scripts` folder in the container and edit the appropriate notebook to convert your model to ONNX, or test the accuracy of the conversion using ONNX Runtime.

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Acknowledgements
This container was based on an original [ONNX Converter docker container](https://github.com/Microsoft/onnxconverter) from 2018. The updated ecosystem docker container is the result of the efforts of the [ONNXMLTools](https://github.com/onnx/onnxmltools) team.

## License
[MIT License](../LICENSE)