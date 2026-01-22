# Booking.com Web Scraping

This module is responsible for collecting hotel accommodation data from Booking for the city of Paris.

The collected data is used as an input source for the data ingestion and analytics pipeline.

---

## 🎯 Objective
The goal of this scraping process is to extract structured hotel information in order to analyze pricing trends, user ratings and market competition in the tourism sector.

---

## 🛠️ Technology Used
- Playwright
- Python
- Pandas

---

## 📄 Data Collected
For each hotel, the following information is extracted:
- Hotel name
- Price per night
- User rating
- Average review score
- Number of reviews

The extracted data is stored in CSV format for further processing.

---

## ⚙️ Scraping Logic Overview
1. Define check-in and check-out dates
2. Navigate to the Booking.com search results page for Paris
3. Automatically scroll the page until all results are loaded
4. Parse hotel cards and extract relevant fields
5. Store the collected data in a structured CSV file


• checkin_date and checkout_date: The arrival and departure dates for the hotel search.
• page_url: The URL of the search results page on Booking.com for Paris on the specified dates.
• Browser, page: Launch the browser and navigate to the URL.
• page_url: The URL of the search results page on Booking for Paris on the specified dates. : 

<img width="1031" height="557" alt="image" src="https://github.com/user-attachments/assets/71e81f80-daff-4aa5-9f9f-41f23f032058" />


This part of the code allows the page to scroll automatically.
We have initialized an empty list to store hotel information. The while loop will allow the page to scroll to the bottom. If the height of the page has not changed, it means that all results have been loaded, and the loop ends : 

<img width="1033" height="575" alt="image" src="https://github.com/user-attachments/assets/061fc290-15ba-43db-997b-b85e888b3199" />

This part of the code extracts and organizes hotel information from the hotel cards
visible on the web page. The code selects all the hotel cards visible on the web page, then scans each card to extract key information. For each hotel, a dictionary is created to store the name, price (or ‘N/A’ if missing), rating, average review score, and number of reviews. Each dictionary is then added to a list, allowing the retrieved data to be grouped and organized :

<img width="1031" height="548" alt="image" src="https://github.com/user-attachments/assets/68eb13ef-234c-4d98-8824-9c8896a409db" />

This part of the code saves the data to an Excel and CSV file.
The code converts the list of dictionaries into a pandas DataFrame, then saves this DataFrame in Excel and CSV format :

<img width="1026" height="300" alt="image" src="https://github.com/user-attachments/assets/ab10dff2-55cf-4759-9323-048055b7e5fd" />


