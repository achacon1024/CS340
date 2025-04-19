# CS340
CS 340 README Template


About the Project/Project Title
This Rescue Dog Dashboard for Grazioso Salvare is a full stack web application that will help identify shelter dogs that could be utilized for search and rescue training.
The application includes:
•	a MongoDB database that stores Austin Animal Center outcome data,
•	a reusable CRUD module,
•	and an interactive Dash dashboard  that has a data table, a geolocation map, and a breed frequency chart.

Motivation
Grazioso Salvare trains rescue dogs worldwide. Instead of going through a slow manual review process, we created a dashboard that filters by rescue type (Water, Mountain/Wilderness, Disaster/Tracking) and shows each dog’s location so trainers can act quickly.

Getting Started
1.	Clone the repository or download the ZIP.
2.	Run MongoDB and import the AAC dataset.
3.	Create the aacuser / SNHU1234 account with readWrite access to the AAC.animals collection.
4.	Open Jupyter and run ProjectTwoDashboard.ipynb, the dashboard opens in the program.

Installation
Before running the project, install the required tools:
1.	PyMongo
2.	MongoDB
3.	Pandas
4.	Dash
5.	Jupyter Notebook

Usage
Use this space to show useful examples of how your project works and how it can be used. Be sure to include examples of your code, tests, and screenshots.

Code Example
from animal_shelter_crud import AnimalShelter
shelter = AnimalShelter("aacuser","SNHU1234",
                        "nv-desktop-services.apporto.com",33251,
                        "AAC","animals")

# Find water‑rescue candidates
water_dogs = shelter.read({
    "animal_type":"Dog",
    "breed":{"$regex":"(?i)(Newfoundland|Chesapeake Bay Retriever|Labrador Retriever)"},
    "age_upon_outcome_in_weeks":{"$lte":104}
})
print(len(water_dogs), "water‑rescue dogs ready for training")

Tests
Run ProjectTwoDashboard.ipynb and switch each radio button:
Water Rescue           ✅ table filtered, map marker moves
Mountain / Wilderness  ✅
Disaster / Tracking    ✅
Reset                  ✅ full dataset


Contact
Your name: Andrew Chacon andrew.chacon@snhu.edu
