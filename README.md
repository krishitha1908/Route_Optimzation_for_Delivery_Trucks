# Route Optimization for delivery trucks

This project is a web application designed to optimize delivery routes using the Traveling Salesman Problem (TSP) algorithm.

## Core Functionality

### 1. Route Optimization
The application solves the Traveling Salesman Problem (TSP) to find the most efficient route between multiple delivery points. It offers two optimization methods:
- **Distance-based optimization**: Finds the shortest route based on geographical distance between points
- **Time-based optimization**: Finds the fastest route based on estimated travel time between points

### 2. Map Interface
The application provides an interactive map interface where users can:
- Click on the map to add delivery points
- Search for locations and add them as delivery points
- Right-click on markers to remove delivery points
- Visualize the optimized route on the map

### 3. Route Visualization
After optimization, the application displays:
- The complete route on a map with markers for each stop
- Different colored markers for start, intermediate stops, and end points
- Pop-up information showing the address of each delivery point

### 4. PDF Report Generation
Users can generate and download a PDF report of the optimized route, which includes:
- Truck ID
- Timestamp of report generation
- Complete list of delivery locations in order

## Tech Stack

### Backend
- Python : Core programming language
- Flask : Web framework for handling HTTP requests, routing, and serving the application
- MongoDB : NoSQL database used for storing cost matrices and caching optimization results
- PyMongo : Python driver for MongoDB integration
- ReportLab : PDF generation library for creating delivery route reports
### Frontend
- HTML/CSS/JavaScript : Core web technologies
- Leaflet.js : JavaScript library for interactive maps
- Leaflet Routing Machine : Extension for displaying routes on maps
- jQuery : JavaScript library for DOM manipulation and animations
### APIs
- OpenRouteService API : External service for calculating real-time travel distances and durations
- Nominatim API : Geocoding service for converting coordinates to addresses and vice versa

## Data Flow
1. User selects delivery points on the map  
2. Application sends coordinates to the backend  
3. Backend calculates the cost matrix (distance or time) between all points  
4. TSP algorithm finds the optimal route  
5. Results are stored in MongoDB for caching  
6. Optimized route is displayed on the map  
7. User can generate a PDF report of the route  

## Optimization Algorithms
The project implements the TSP algorithm using dynamic programming with memoization for efficient route calculation. It can optimize based on:
1. Haversine distance (straight-line distance between coordinates)  
2. Real-time travel time data from OpenRouteService API  

The application caches results in MongoDB to improve performance for repeated queries.
