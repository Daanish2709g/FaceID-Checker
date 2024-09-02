# FaceID-Checker

## Setup

### Prerequisites

- Python 3.8 or higher
- ChromeDriver
- VPN extension (`VPN-extension.crx`)

- ## Features

- Bypass captchas using a VPN (accuracy of bypass is approximately 50%).
- Upload Pictures to the FaceCheck ID website.
- Extract URLs of sites where the image appears.
- REST API for uploading pictures and Getting results.
- an Social media bot for easy interaction and image processing.

- ## Overview

The FaceID Check is a Python tool that leverages Selenium for web scraping and circumvents captchas by utilizing a VPN. The tool is built to upload images to the FaceCheck ID website, manage captcha challenges, and retrieve URLs where the image is found. It also integrates a REST API built with Flask and a Telegram bot for user-friendly interaction.

### Installation

1. **Install Required Packages**
   ```bash
   pip install -r requirements.txt
   ```

2. **Add VPN Extension**
   Place the VPN extension (`VPN-extension.crx`) in the project directory.
   
## Usage

### Running the Scraper

To run the scraper, execute the following script:

```python
from scraper import Scraper

image_path = r"absolute_path_to_your_image.jpg"
scraper = Scraper()
scraper.main(image_path)
```

### REST API

#### Starting the Flask Server

```bash
python api.py
```

#### API Endpoints

1. **Upload Image**
   - **Endpoint**: `/upload`
   - **Method**: POST
   - **Description**: Uploads an image and starts the scraping process.
   - **Parameters**: Form-data with key `image` (file)


2. **Get Results**
   - **Endpoint**: `/results/<image_id>`
   - **Method**: GET
   - **Description**: Retrieves URLs where the image appears.
   - **Parameters**: `image_id` (string)
  
   - ![Screenshot 2024-09-03 011213](https://github.com/user-attachments/assets/eab2c32b-b9ad-4010-8c55-5350d5b8d388)



```bash
python bot.py
```

#### Uploading an Image

Send an image through the Social media bot to start the scraping process. The bot will process the image and return URLs where the image appears.

## Captcha Handling

For scraping data, Selenium and a VPN are used to bypass captchas with an accuracy of approximately 60%. The tool attempts to handle captchas using a VPN by toggling it on and off. 

