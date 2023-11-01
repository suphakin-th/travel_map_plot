```python
# Import necessary libraries
import pandas as pd
import folium

# Load the data from the CSV file
file_path = "tourist_attraction.csv"
df = pd.read_csv(file_path)

# Create a map centered around the first location
m = folium.Map(location=[df['latitude'].iloc[0], df['longitude'].iloc[0]], zoom_start=4)

# Add markers for each location
for index, row in df.iterrows():
    # Create a marker for each location with a popup displaying place name and description
    folium.Marker(
        location=[row['latitude'], row['longitude']],
        popup=f"{row['place_name']} - {row['description']}",
        icon=folium.Icon(color='blue')  # Set the marker color to blue
    ).add_to(m)  # Add the marker to the map

# Display the map
m

Explanation:

- The code is enclosed within triple backticks (```) to format it as a code block.
- This Markdown code is meant to be placed in a Markdown cell in a Jupyter Notebook.
- The Python code will be properly formatted and highlighted when rendered in the Markdown cell.
