
## Animal Endangerment Tracker

### Overview
The **Animal Endangerment Tracker** is a **MongoDB-based database concept** designed to store and manage data on endangered species, conservation efforts, and environmental threats. The goal is to provide a structured and scalable solution for tracking animal populations, risk factors, and conservation initiatives worldwide.

### Features
- **NoSQL database structure** optimized for fast queries and scalability.
- **Species tracking** with key attributes like conservation status, habitat, and population trends.
- **Threat analysis** to document environmental and human-related risks.
- **Conservation initiatives database** to log efforts aimed at preserving species.
- **Geo-tagged data** for location-based insights on endangered species.

### Technologies Used
- **MongoDB** (Primary NoSQL database)
- **Python/PyMongo** (Database interaction)
- **JSON Schema** (Data structuring)
- **Flask (Future Implementation)** (Potential API development)

### Database Structure
```json
{
  "species_name": "Panthera tigris",
  "common_name": "Bengal Tiger",
  "conservation_status": "Endangered",
  "population_estimate": 2500,
  "habitat": "Forests, Grasslands",
  "primary_threats": ["Poaching", "Deforestation", "Climate Change"],
  "conservation_efforts": [
    {
      "initiative_name": "Project Tiger",
      "organization": "WWF",
      "year_started": 1973,
      "impact": "Increase in protected reserves"
    }
  ],
  "geo_location": {
    "latitude": 26.9124,
    "longitude": 75.7873
  },
  "last_updated": "2025-03-12"
}
```

### Installation & Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Animal-Endangerment-Tracker
   cd Animal-Endangerment-Tracker
   ```
2. Install dependencies:
   ```bash
   pip install pymongo flask jsonschema
   ```
3. Set up MongoDB:
   - Install MongoDB and start a local or cloud instance.
   - Create a database named `animal_tracker`.
   - Import sample data:
     ```bash
     mongoimport --db animal_tracker --collection species --file species_data.json --jsonArray
     ```
4. Connect to MongoDB:
   ```python
   from pymongo import MongoClient

   client = MongoClient("mongodb://localhost:27017/")
   db = client["animal_tracker"]
   collection = db["species"]

   # Fetch sample data
   for doc in collection.find():
       print(doc)
   ```
5. Expand functionality with **APIs** or **data visualization**.

### Future Improvements
- **Integration with real-time conservation data sources** (e.g., IUCN Red List, WWF).
- **Web-based dashboard** for interactive data visualization.
- **AI-powered risk assessment** for predicting species survival probabilities.
