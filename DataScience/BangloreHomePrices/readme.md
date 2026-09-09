# Bangalore Home Price Prediction

![Bangalore Home Price Prediction UI](BHP_website.PNG)

This project demonstrates an end-to-end machine learning application for predicting Bangalore home prices. It covers data preparation, feature engineering, outlier handling, model selection, a Flask API, and a browser-based UI.

## Project structure

```text
BangloreHomePrices/
├── client/                 # HTML, CSS, and JavaScript UI
├── model/                  # Training notebook and model metadata
├── server/                 # Flask API and saved model artifacts
├── nginx_files/            # Nginx deployment configuration
└── readme.md
```

## Technologies

- Python
- NumPy and Pandas
- Matplotlib
- scikit-learn
- Jupyter Notebook
- Flask
- HTML, CSS, and JavaScript
- Nginx (optional, for deployment)

## Run locally

1. Open a terminal in `BangloreHomePrices/server`.
2. Create and activate a virtual environment:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

   On Windows PowerShell, use `.venv\Scripts\Activate.ps1` instead.

3. Install the server dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Start the Flask server:

   ```bash
   python server.py
   ```

5. Open `client/app.html` in a browser. The UI expects the Flask API to be available on `http://127.0.0.1:5000`.

> The saved model and `columns.json` are already included in `server/artifacts`, so retraining is not required to run the demo.

## API endpoints

### `GET /get_location_names`

Returns the locations supported by the trained model.

### `POST /predict_home_price`

Accepts these form fields:

- `total_sqft`: total area in square feet
- `location`: supported location name
- `bhk`: number of bedrooms
- `bath`: number of bathrooms

Example with `curl`:

```bash
curl -X POST http://127.0.0.1:5000/predict_home_price \
  -d "total_sqft=1000" \
  -d "location=1st Phase JP Nagar" \
  -d "bhk=2" \
  -d "bath=2"
```

## Deployment notes

For an AWS EC2 deployment, install Nginx and configure it to serve the `client` directory while proxying `/api/` requests to Flask. Before deployment, update the Nginx `server_name`, verify the application paths, and restrict cloud firewall rules to only the ports you need.

Do not commit private SSH keys, cloud credentials, or machine-specific paths to the repository.

## Contributing

Small improvements are welcome. Before opening a pull request:

1. Keep changes focused on one problem.
2. Update documentation when behavior or setup instructions change.
3. Test the affected code locally.
4. Use a clear commit message describing the change.
5. Do not add credentials, private keys, or generated environment-specific files.
