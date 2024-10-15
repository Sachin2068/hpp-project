import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
import pickle

# Load the dataset
data = pd.read_csv("house_data.csv")

# Feature columns
X = data[["area", "bedrooms", "bathrooms"]]

# Target column (price)
y = data["price"]

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train the model
model = LinearRegression()
model.fit(X_train, y_train)

# Save the trained model to a file
with open("house_price_model.pkl", "wb") as f:
    pickle.dump(model, f)

print("Model trained and saved!")
