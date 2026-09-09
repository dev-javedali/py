# Celebrity Face Recognition

![Celebrity Face Recognition UI](ui_snapshot.jpg)

This project demonstrates a computer-vision pipeline that classifies images of five sports personalities:

1. Maria Sharapova
2. Serena Williams
3. Virat Kohli
4. Roger Federer
5. Lionel Messi

## Project structure

```text
CelebrityFaceRecognition/
├── UI/                         # Browser interface
├── server/                     # Flask API and model artifacts
├── model/                      # Model-training notebook and dependencies
├── google_image_scrapping/     # Optional dataset collection utility
└── images_dataset/             # Training images
```

## Technologies

- Python
- NumPy
- OpenCV
- Matplotlib and Seaborn
- scikit-learn
- Jupyter Notebook
- Flask
- HTML, CSS, and JavaScript

## Running the server

1. Open a terminal in `CelebrityFaceRecognition/server`.
2. Create and activate a virtual environment:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install the dependencies required by the server/model environment.
4. Start the Flask server:

   ```bash
   python server.py
   ```

The API listens on port `5000` by default.

## Dataset collection

The `google_image_scrapping` directory contains an optional utility for collecting training images. Web pages and browser automation tools can change over time, so use the script only when you need to rebuild the dataset and verify that the browser-driver version matches the installed Selenium version.

Respect the terms of service and copyright/license requirements of image sources when collecting or redistributing datasets.

## Notes for contributors

- Keep model artifacts and datasets reproducible where possible.
- Avoid committing personal data, credentials, or machine-specific browser-driver binaries.
- Keep pull requests focused and explain how changes were tested.

## Original tutorial

The project was created as part of a data-science tutorial series. The original video playlist is available on YouTube:

https://www.youtube.com/playlist?list=PLeo1K3hjS3uvaRHZLl-jLovIjBP14QTXc
