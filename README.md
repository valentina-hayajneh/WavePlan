# Web Microwave Planning Tool (WavePlan)


## 🌐 Overview

A web-based interactive tool was developed for microwave link planning and design, aimed at enabling engineers and researchers to simulate wireless infrastructure with high precision and realism—directly from the browser and without the need for any additional software. To enhance the accuracy of the planning process, the tool supports three distinct map layers: OpenStreetMap for flexible visualization of roads and buildings, Satellite View for high-resolution terrain and natural features, and Terrain View to highlight the geographical factors affecting link quality. This combination of mapping options allows users to simulate network layouts in urban, rural, and mountainous environments with realistic visual context, leading to more accurate technical assessments and better-informed engineering decisions.

<img width="1916" height="852" alt="image" src="https://github.com/user-attachments/assets/0f617158-f6d1-4a1b-abc8-c96026c32117" />

**Figure 1**: Tool’s main interface with satellite view
---

## How It Works
Users start by placing tower markers anywhere on the map, where they can assign custom names, heights, and tower types such as lattice, monopole, or guyed towers. These towers can then be linked together using microwave links.

## Topology Support: Star & Ring

To support more advanced network design, the tool includes built-in topology options—specifically Star and Ring formations. These structures are commonly used in real-world microwave networks to improve redundancy, efficiency, and scalability.

In Star topology, all microwave links originate from a central tower (hub) and connect to surrounding nodes. This setup is ideal for centralized architectures such as rural internet distribution or urban backhaul centers.

<img width="886" height="690" alt="image" src="https://github.com/user-attachments/assets/d0593edf-1101-48b4-b412-156d1564036c" />

**Figure 2**: Star topoly 

In Ring topology, towers are connected in a closed loop. This allows for fault tolerance—if one link fails, data can still circulate in the opposite direction.

<img width="809" height="731" alt="image" src="https://github.com/user-attachments/assets/63133b5a-6038-4bc2-a6aa-8dc1e7333ac5" />

**Figure 3**: Ring topology

These topology modes save significant time during design and help simulate realistic multi-point or resilient networks efficiently. All link budget calculations, frequency assignments, and path loss estimations are automatically applied per link, even in complex topologies.

The tool performs detailed link budget calculations to ensure microwave links are planned with high accuracy and reliability. This process begins by calculating the precise distances between towers using the Vincenty formula, which accounts for the Earth's ellipsoidal shape to achieve sub-meter accuracy—much more precise than simpler formulas like Haversine.The tool performs detailed link budget calculations to ensure microwave links are planned with high accuracy and reliability.

<img width="1226" height="476" alt="image" src="https://github.com/user-attachments/assets/1f15d099-9b18-424c-8806-5513eff4f25b" />

**Figure 4**: distance between two markers(towers) located in Irbid

Based on these distances, the tool dynamically assigns appropriate frequency bands to each link, optimizing for path loss, antenna size, and data rate requirements,Accordingly, short-range links under 1 km utilize the 38 GHz band, suitable for dense urban cores, whereas longer links up to 20 km use lower frequency bands such as 18 GHz to maintain stable connections over greater distances. 
This distance-based frequency allocation was integrated into the planning tool to automate frequency assignment

<img width="592" height="353" alt="image" src="https://github.com/user-attachments/assets/a3921b50-92a8-4b59-b54d-ef36eeee8c62" />

**Figure 5**: approved frequencies according to the  distance

Next, the tool calculates the Free Space Path Loss (FSPL) using the standard logarithmic equation, considering both the frequency and distance. This helps estimate the expected signal attenuation over the link.

Antenna gain is then factored in, based on antenna size and frequency, which enhances the signal strength in the desired direction.

<img width="604" height="221" alt="image" src="https://github.com/user-attachments/assets/ee184cef-c4dc-49eb-87b5-36e21fdaa529" />

**Figure 6**: FSPL and antenna gain for two towers allocated in Irbid 

**Note**:  antenna gain is calculated automatically ,but user can exchange the value according to the required design 
---
The tool also accounts for cable and connector losses based on the type, the supported cable types include LMR-400, LMR-600, RG-58, RG-213, Heliax-1/2, Heliax-7/8, 
and Waveguide, each exhibiting unique attenuation characteristics , as illustrated in Figure 5, in addition to cable losses, connector losses are also taken into consideration based on the number 
of connectors and their quality classification. Each connector introduces a fixed attenuation depending on its quality: 0.1 dB for high quality, 0.25 dB for medium quality, and 0.5 dB for low 
quality

<img width="601" height="565" alt="image" src="https://github.com/user-attachments/assets/9bd55309-41ca-4c4b-8f5f-efd32662591b" />

**Figure 7**: cable losses 

Finally, all these parameters are combined to estimate the received power at the destination antenna (in this project we using the parabolic antenna ) ,This comprehensive calculation allows users to evaluate link feasibility, detect potential issues, and adjust design parameters in real-time, ensuring optimal network performance.

<img width="1173" height="726" alt="image" src="https://github.com/user-attachments/assets/0078bb83-d362-4efe-b5b3-171fdf9c8501" />

**Figure 8**: received power 
---
## summary 
This project delivers a well-structured, browser-based microwave link planning tool designed for high accuracy, usability, and realism. By combining precise geodesic calculations, dynamic link budget analysis, and support for multiple map views, the tool offers a practical and intuitive environment for engineers and researchers. From frequency allocation to received power estimation, each feature is seamlessly integrated to reflect real-world conditions. The result is a reliable, easy-to-use platform that supports informed decision-making and professional network design—all from within the browser.
