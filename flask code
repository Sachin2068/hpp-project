from flask import Flask, request, jsonify
import pickle
import numpy as np

app = Flask(__name__)

# Load the trained machine learning model
with open("house_price_model.pkl", "rb") as f:
    model = pickle.load(f)

@app.route("/predict", methods=["POST"])
def predict():
    data = request.get_json()

    area = data["area"]
    bedrooms = data["bedrooms"]
    bathrooms = data["bathrooms"]

    # Prepare the data for prediction
    features = np.array([[area, bedrooms, bathrooms]])

    # Get prediction from the model
    prediction = model.predict(features)[0]

    # Return the prediction as a JSON response
    return jsonify({"price": prediction})

if __name__ == "__main__":
    app.run(debug=True)
