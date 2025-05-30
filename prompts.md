# 📄 prompts.md — ChatGPT Prompts Used to Create the Interactive Map

This file documents the main prompt and the workflow used to generate a Python script for building an interactive map of protest-related incidents using ChatGPT and Folium.

---

## 🎯 Goal

Create a **Python script** (for **Google Colab**) that:
- Loads data from a **public Google Sheet**
- Displays incidents on an **interactive map** using **Folium**
- Uses custom **icons**, **colors**, and **popups**
- Adds a **legend**, **logo**, and **footer**
- Saves the map as an `.html` file

---

## 🧠 Initial Prompt

```
Create a Python script I can run in Google Colab to generate an interactive map from a public Google Sheets file containing incidents. The data includes the following columns:

* city
* precise location (textual location detail within the city)
* latitude
* longitude
* date
* description (text describing the incident)
* source link (URL to source)
* source (name of source)
* type of incident (category: bat, car, fight, pushing/hitting, other)

The code must:

1. Load the data from this public Google Sheet:
   https://docs.google.com/spreadsheets/d/1fSLQ4tYyAPDP1PvdYoIkteiuCvtA0P1MKDcXv9oawQI/edit?usp=sharing

2. Display each incident as a marker on the map, with:
    - Slight adjusting locations to avoid overlapping if incidents share the same coordinates
    - Custom icons and colors based on the type of incident:
        - bat → fa-tools, dark red
        - car → fa-car, blue
        - fight → fa-user-friends, green
        - pushing/hitting → fa-hand-rock, orange
        - other → fa-question-circle, gray

3. Each marker should have a popup that shows:
    - Date, City, Precise Location, Description
    - The Source name as a hyperlink from source link, opening in a new tab

4. The map should include:
    - A headline: “Attacks on Protest and Blockade Participants” — bold, black, centered, using Arial
    - A footer: “Data collected by CINS” where “CINS” is a hyperlink to https://www.cins.rs/en/, opening in a new tab
    - A logo in the bottom right corner (width ≈ 100px), from:
      https://www.cins.rs/wp-content/themes/cins-V2/assets/logo.png
    - A legend that visually explains icon + color mapping for each incident category

5. Use a clean and professional tile layer

6. Use MarkerCluster to group nearby markers when zoomed out

7. Style all popups with Arial font and font size around 13px

8. Save the final map as incident_map.html, ready for download in Colab
```

---

## 🔄 ChatGPT Helped With

- Setting up Google Sheets access using `gspread` and `pandas`
- Creating a map with `folium`, including:
  - Marker clustering
  - Custom icons, colors, and popups
  - Layout: header, legend, footer, logo
- Exporting the final output as `incident_map.html`
- Debugging small issues along the way

---

## 💡 Tips from the Process

> Based on internal training material used for this exercise:

- ✅ Write prompts like you’re talking to a colleague
- ✅ Be specific: source, categories, colors, fonts, expected output
- ✅ Use examples if needed
- ✅ If errors happen, copy-paste them into ChatGPT and ask for help
- ✅ Ask ChatGPT to suggest improvements or explain code
- ✅ Use Google Colab or Jupyter for safe testing
- ✅ Keep a working version of your file before experimenting

---

## 📎 Related Files

- `incident_map.ipynb` — Final Colab notebook
- `incident_map.html` — Exported result (optional)
- `README.md` — Guide for running the project and working with ChatGPT

---
