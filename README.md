
# Zoe Depth Estimation API

Welcome to the Zoe Depth Estimation API repository. This project utilizes deep learning to estimate depth from single images, leveraging the power of PyTorch and FastAPI for efficient and scalable depth estimation services.

## Features

- **Single Image Depth Estimation**: Predicts depth from a single RGB image.
- **FastAPI Integration**: Provides a seamless and high-performance API for easy integration into various applications.
- **PyTorch-based Model**: Utilizes a pre-trained depth estimation model in PyTorch for accurate and efficient predictions.
- **Docker Support**: Dockerfile included for easy containerization and deployment.

## Getting Started

Follow these instructions to set up and run the Zoe Depth Estimation API on your local machine.

### Prerequisites

Ensure you have the following installed:

- Python 3.8+
- Docker (optional, for containerized deployment)

### Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/recepayddogdu/Zoe-Depth-Estimation-API.git

    cd Zoe-Depth-Estimation-API
    ```

2. **Create and activate a virtual environment** (optional but recommended):

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install the required packages**:

    ```bash
    pip install -r requirements.txt
    ```

### Configuration

This project uses a `.env` file to manage configuration variables. Below are the steps to set up the `.env` file:

1. **Create a `.env` file** in the root directory of the project:

    ```bash
    touch .env
    ```

2. **Add the required configuration variables** to the `.env` file. Here is an example of what the `.env` file might contain:

    ```env
    # .env
    IMGBB_API_KEY=your_api_key_here
    ```

    - `IMGBB_API_KEY`: Your API key for authenticating requests to the IMGBB service.

### Usage

1. **Run the FastAPI server**:

    ```bash
    uvicorn main:app --reload
    ```

2. **Access the API**:

    Open your browser and navigate to `http://127.0.0.1:8000/docs` to see the interactive API documentation provided by FastAPI Swagger UI.

3. **Test the API**:

    You can use tools like `curl`, `Postman`, or the FastAPI docs interface to test the endpoints. For example, to estimate depth from an image:

    ```bash
    curl -X 'POST'\
        'http://127.0.0.1:8000/predict'\
        -H 'accept: application/json'\
        -H 'Content-Type: multipart/form-data'\
        -F 'file=@path_to_your_image'
    ```

### Docker Deployment

To run the API in a Docker container, follow these steps:

1. **Build the Docker image**:

    ```bash
    docker build -t zoe-depth-estimation-api .
    ```

2. **Run the Docker container**:

    ```bash
    docker run -d -p 8041:8041 zoe-depth-estimation-api
    ```

3. **Access the API**:

    Open your browser and navigate to `http://127.0.0.1:8041/docs`.

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. **Fork the repository**.
2. **Create a new branch** (`git checkout -b feature/YourFeature`).
3. **Commit your changes** (`git commit -am 'Add new feature'`).
4. **Push to the branch** (`git push origin feature/YourFeature`).
5. **Create a new Pull Request**.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any questions or suggestions, please contact:

- Recep Aydoğdu - [Email](mailto:recepayddogdu@gmail.com)
- GitHub: [recepayddogdu](https://github.com/recepayddogdu)
