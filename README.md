# nosql-challenge
## Eat Safe, Love: UK Food Standards NoSQL Analysis
This assignment focuses on analyzing food hygiene ratings data from the UK Food Standards Agency to help "Eat Safe, Love" magazine writers decide where to focus future articles.
The assignment was divided into two notebooks **NoSQL_setup.ipynb** and **NoSQL_analysis.ipynb**.

## Setup Notebook
### Part 1: Database and Jupyter Notebook Set Up
- The database was initialized and data was imported from the provided establishments.json file.
- The data is stored in the uk_food database and the establishments collection.
- Used the **pymongo** library to establish a connection to the MongoDB server and performed basic data exploration.

### Part 2: Update the Database

- Added a new restaurant: Added "Penang Flavours", a new restaurant located in Greenwich, into the collection.

- Retrieved BusinessTypeID: Found the BusinessTypeID associated with "Restaurant/Cafe/Canteen".

- Updated BusinessTypeID: Updated the new restaurant's document to include the retrieved BusinessTypeID.

- Removed establishments from Dover: Found and deleted all establishments associated with the Dover Local Authority.

- Data type correction:
    - Converted the latitude and longitude fields to decimal numbers for all documents.
    - Converted the RatingValue field to integer numbers for all documents, setting non-integer ratings to Null.

## Exploratory Analysis
The Jupyter Notebook content **NoSQL_analysis.ipynb** centers on exploratory data analysis of a MongoDB database that stores data on various food establishments.

Here's a brief rundown of the analysis:

1. **Establishments with a hygiene score of 20:**

    - The establishments with a hygiene score of 20 are queried.
    - The results are summarized with the number of matches, printed out, and converted to a Pandas DataFrame for further visualization.

2. **London establishments with a high rating:**

    - The establishments located in London with a RatingValue greater than or equal to 4 are identified.
    - This section gives insights into high-performing establishments within the London area.

3. **Proximity Analysis with a High Rating:**

    - For the newly added restaurant "Penang Flavours", other establishments with a RatingValue of 5 are searched within a proximity range.
    - These results are sorted by hygiene score, providing insights into how well nearby competitors perform in terms of hygiene. This can be particularly useful for strategizing improvements for "Penang Flavours".

4. **Local Authority Analysis:**

    - An aggregation pipeline is used to count the number of establishments in each local authority with a hygiene score of 0.
    - This section provides insights into which areas might be in need of improved oversight or where hygiene practices are subpar.


## Source Code:
- PyMongo 4.5.0 Documentation <https://pymongo.readthedocs.io/en/stable/>
- pandas documentation <https://pandas.pydata.org/docs/>

## References:
[UK Food Standards Agency](https://www.food.gov.uk/). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GB Contains public sector information licensed under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/)
Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).