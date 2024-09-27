# Deploying an OCR Service

## Overview
This repository contains the necessary files and instructions to deploy an Optical Character Recognition (OCR) service. The OCR service is built using a deep learning model and can be used to extract text from images.

## Prerequisites
Before you begin, ensure that you have the following installed on your system:

- Docker
- Docker Compose

## Getting Started

1. **Clone the repository**:
   ```
   git clone https://github.com/your-username/ocr-service.git
   cd ocr-service
   ```

2. **Build the Docker image**:
   ```
   docker-compose build
   ```

3. **Start the OCR service**:
   ```
   docker-compose up -d
   ```

   This will start the OCR service in the background.

## Usage

To use the OCR service, you can send an HTTP POST request to the `/ocr` endpoint with an image file attached. The service will respond with the extracted text.

Example using cURL:

```
curl -X POST -F 'image=@/path/to/image.jpg' http://localhost:8000/ocr
```

The response will be a JSON object containing the extracted text:

```json
{
  "text": "This is the text extracted from the image."
}
```

## Configuration

The OCR service can be configured using environment variables. The following variables are available:

- `MODEL_PATH`: The path to the pre-trained OCR model. Default is `./model/ocr_model.pth`.
- `PORT`: The port on which the service will run. Default is `8000`.

To set these variables, you can modify the `docker-compose.yml` file.

## Development

If you want to modify the OCR model or the service itself, you can do so by editing the corresponding files in the `src/` directory. Once you've made your changes, rebuild the Docker image and restart the service.

## License

This project is licensed under the [MIT License](LICENSE).
