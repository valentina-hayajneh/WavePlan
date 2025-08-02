# Wireless Microwave Link Planning Tool

This interactive web-based application is tailored for wireless microwave link planning and analysis between tower sites. Designed with engineers, planners, and geospatial professionals in mind, the tool offers a rich, map-based interface for placing towers, drawing links, and computing link performance metrics.

🧭 Overview and Functionality
Users can dynamically add tower markers to a map with custom properties such as type, height, and location coordinates. These towers can then be connected via microwave links, enabling detailed link budget calculations, which consider parameters like transmitted power, antenna gain, cable and connector losses, and free-space path loss. The tool calculates critical values such as RX power. 

The application provides several map layers including satellite imagery, OpenStreetMap, and terrain elevation, allowing users to visualize the environment and assess feasibility more accurately. Users can also toggle labels, markers, and layer visibility for a more customizable experience.

⚙️ Core Features
Antenna Configuration Panels: Detailed UI panels allow users to set antenna type, diameter, height, efficiency, and gain values (manual or auto-computed).

Link Budget Calculator: Computes complete signal path losses including TX/RX losses, connector types, cable lengths, and generates the final RX power.

Interference Detection: A basic mechanism highlights frequency conflicts and link intersections that may cause signal interference.

Network Topologies: The tool supports predefined topologies such as Star and Ring, automatically arranging nodes.

Search & Geolocation: Built-in search bar allows users to find specific locations or enter lat/lon directly.

Project Management: Users can create, save, and export projects, including the option to export links as KML files for GIS platforms.
#Screenshots & Descriptions:
Pic 1:  
This interface displays a detailed satellite view of a city with multiple markers indicating key locations. Users can utilize the search bar to quickly find any location by name or coordinates. Additionally, an "Add Marker" button allows users to easily place new markers (towers) on the map, enabling dynamic updates and customization of the network layout.

Pic 2:  
This interface displays the tower's properties, allowing users to search for or manually add a tower. It provides the tower’s name with the option to edit it, the ability to select the tower type and height, and automatically stores the tower's coordinates (marker) from the map upon placement.

Pic 3:  
This web application supports two types of topologies: Star topology, where the first added tower acts as the central hub connected to surrounding towers, and Ring topology, which creates a closed loop starting from the first added tower and connecting sequentially to others. This sequential setup ensures that the initial tower defines the topology’s starting point, whether as a center in star topology or the beginning of the ring in ring topology.

Pic 4:  
This interface displays the link properties between towers, allowing users to specify the cable type, length, number of connectors, and connector quality for both transmission and reception. Based on these inputs, the system automatically calculates the total signal loss, ensuring accurate and efficient network planning.

Pic 5:  
Link properties between two selected towers. It shows the distance in meters and kilometers, transmission frequency (GHz), TX power (dBm), antenna height, and diameter. The system is designed to use a fixed Parabolic antenna type for all microwave links to ensure high-gain and directional transmission efficiency.

Pic 6:  
This interface displays extended link properties between two selected towers. It includes detailed antenna specifications such as the fixed Parabolic type, diameter, aperture area, and wavelength. It also shows calculated values like TX/RX gain (dB), Free Space Path Loss (FSPL), and received power (RX Power). These parameters ensure accurate link budget estimation and reliable microwave communication planning.

Pic 7:  
This image shows the interference detection feature in action. It identifies overlapping microwave links (MW Link 1 and MW Link 2) that are using the same frequency (8 GHz) at a common tower location. The conflict is visually highlighted in red, and a detailed popup provides the interference type and affected tower coordinates, helping users quickly resolve frequency planning issues.
