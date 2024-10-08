<h1>Splunk4Rookies - Workshop</h1>

 </h2>

<h2>Case Study: </h2>
At the Splunk4Rookies workshop, my case study involved Buttercup Enterprises, a large national online retailer based in the US, offering a wide range of products including books, clothing, and gifts through its online webstore.

Buttercup Enterprises has recently made a significant investment in Splunk and is eager to integrate its capabilities across the business.

Your Role

- You are among the select few: a Splunk power user!
- Your primary responsibility is to deliver actionable insights to users across various departments.

The teams you support include

- IT Operations
- DevOps
- Business Analytics
- Security and Fraud

Overview of Tasks

- Strengthening digital resilience with Splunk
- Developing a custom Splunk app
- Integrating diverse datasets
- Conducting searches and generating reports
- Creating new data fields
- Utilising lookup tables effectively
- Designing versatile dashboards for multiple scenarios. <br />


<h2>Part 1: Creating an App and Adding Data into Splunk</h2>
<br />

<b>Steps:</b> 

<p>1. I logged in to Splunk using admin credentials.</p>
<p>2. On the left side of the page, under the Apps section, I clicked on Manage.</p>
<p align="center">
<img src="https://imgur.com/1GLyq8M.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>3. In the top right corner of the screen, I clicked on Create app.</p>
<p align="center">
<img src="https://imgur.com/B6zrEJ1.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>4. I named the app and entered a folder name, leaving other values as default, and clicked Save.</p>
<p align="center">
<img src="https://imgur.com/7R8QayB.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>5. Once created, I selected the app to ensure all subsequent actions are within its scope.</p>
<p align="center">
<img src="https://imgur.com/WskPYq3.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>6. To select the app, I clicked on the Apps dropdown list at the top left and chose the app.</p>
<p>7. With the app selected, I navigated to Settings > Add Data.</p>
<p align="center">
<img src="https://imgur.com/jFywd2k.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>8. For this exercise, I chose to monitor a directory to capture data generated by the web server. I clicked on Monitor.</p>
<p align="center">
<img src="https://imgur.com/yHc1Twx.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>9. Selecting Files & Directories, I browsed to /var/log and chose the weblogs directory, clicking Select.</p>
<p align="center">
<img src="https://imgur.com/pizm9Q6.png" height="65%" width="65%" alt=""/>
</p>

<br />
<p>10. I confirmed the directory path (/var/log/weblogs) and clicked Next.</p>
<p align="center">
<img src="https://imgur.com/KWmUhGS.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>11. On the Input Settings screen, I selected a source type by clicking Select next to Source type, choosing Web > access_combined from the dropdown list.</p>
<p align="center">
<img src="https://imgur.com/qgypTGB.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>12. I ensured the new app was selected for App Context.</p>
<p>13. Leaving other settings as default, I clicked Review.</p>
<p>14. After reviewing, I clicked Submit.</p>
<p>15. A message confirmed the successful creation of the file input. I clicked Start Searching to explore the data in Splunk.</p>
<p align="center">
<img src="https://imgur.com/TgHylFA.png" height="65%" width="65%" alt=""/>
</p>

<br />

<p>16. I verified raw events were displayed in Splunk.</p>

<p align="center">
<img src="https://imgur.com/u9XkvF0.png" height="65%" width="65%" alt=""/>
</p>

<br />


<b>Exploring my Data</b> 
<p>In this exercise, I explored basic Splunk searches using the Search section of my new app.</p>

<p>In the Splunk environment:</p>

 
<p>•503 purchase searches for events containing the status code "503" and the word "purchase".</p>

<p align="center">
<img src="https://imgur.com/h8HKyM5.png" height="65%" width="65%" alt=""/>
</p>


<p>•503 pur searches for events containing the status code "503" and the fragment "pur"..</p>

<p align="center">
<img src="https://imgur.com/9udOvX6.png" height="65%" width="65%" alt=""/>
</p>


<p>Difference: 503 purchase finds events with the full word "purchase," while 503 pur finds events with any word starting with "pur," like "purchase," "purchased," or "purchasing"..</p>
</p>

<br />


<h2>Part 2: IT Operations team: Investigate successful vs unsuccessful web server requests over time
</h2>
<br />

<p>Description:
The IT Operations team at Buttercup Enterprises currently lacks visibility into website failures.</p> 

<b>Steps:</b> 

<p>1. Selecting my app from the Apps dropdown, I clicked Search on the app menu bar.</p>

<p>2. I searched the main index for web server events over the last 60 minutes: `index=main sourcetype=access_combined`.</p>
<p align="center">
<img src="https://imgur.com/0ny82BN.png" height="65%" width="65%" alt=""/>
</p>
<p>3. I located the status field, clicked it, and selected Top values by time.</p>
<p>4. Splunk populated my search: `index=main sourcetype=access_combined | timechart count by status limit=10`.</p>
<p align="center">
<img src="https://imgur.com/zkqsWPL.png" height="65%" width="65%" alt=""/>
</p>
<p>5. Changing the visualisation to a Column Chart on the Visualisation tab.</p>
<p align="center">
<img src="https://imgur.com/eE3gmeD.png" height="65%" width="65%" alt=""/>
</p>
<p>6. Clicking Format, I went to the General tab and set the Stack Mode to 'stacked'. I adjusted formatting as necessary.</p>
<p>7. I saved the chart to a new dashboard via Save As > New Dashboard.</p>
<p align="center">
<img src="https://imgur.com/tF08TPD.png" height="65%" width="65%" alt=""/>
</p>
<p>8. Naming the dashboard appropriately (e.g., 'Buttercup Enterprises') and adding a description if needed.</p>
<p align="center">
<img src="https://imgur.com/2GXsnmJ.png" height="65%" width="65%" alt=""/>
</p>
<p>9. Using Dashboard Studio with Absolute layout mode.</p>
<p>10. I titled the panel appropriately (e.g., 'IT Ops - Web Server Status Codes Over Time').</p>
<p>11. Clicking Save to Dashboard, then View Dashboard.</p>
<p align="center">
<img src="https://imgur.com/S54SrFi.png" height="65%" width="65%" alt=""/>
</p>


<h2>Part 3 – DevOps team: Show the most common customer platforms and operating systems and which web browsers are experiencing the most failures
</h2>
<br />

<p>Description:
In this exercise, I extracted a new field from events using Splunk’s field extractor wizard.
</p> 

<p>Custom field extractions are useful in various scenarios, such as: </p> 

<p>•When I have custom data and Splunk did not recognize/extract a particular field that I need.</p> 

<p>•When I need to extract a specific part of an event to search/report on that value.</p> 
<br />
<b>Extract a New Field</b> 

<b>Steps:</b> 

<p>1. Click Search if the search bar isn't displayed.</p>
<p>2. Search for web server events from the last 60 minutes: `index=main sourcetype=access_combined`.</p>
<p>3. Click the arrow (>) next to an event timestamp to expand it.</p>
<p>4. Click the Event Actions dropdown and select Extract Fields.</p>
<p align="center">
<img src="https://imgur.com/qNMgw2l.png" height="65%" width="65%" alt=""/>
</p>
<p>5. Choose Regular Expression and click Next.</p>
<p align="center">
<img src="https://imgur.com/M16JKVG.png" height="65%" width="65%" alt=""/>
</p>



<p>6. In the sample event, find and highlight the platform info in the useragent string.</p>
<p>7. Name the new field "platform" (use all lowercase).</p>
<p>8. Click Add Extraction, then click Next.</p>
<p align="center">
<img src="https://imgur.com/kYAG1xc.png" height="65%" width="65%" alt=""/>
</p>
<p>9. Click Next again to reach the Save screen, then click Finish.</p>
<p align="center">
<img src="https://imgur.com/EzTA36P.png" height="65%" width="65%" alt=""/>
</p>
<p>10. On the Success page, click Explore the fields I just created in Search.</p>
<p>11. Splunk will show search results for the last 24 hours. Scroll down to see your new field listed on the left. </p>
<p align="center">
<img src="https://imgur.com/NlSmrh2.png" height="65%" width="65%" alt=""/>
</p>





<h2>Part 4 – Business Analytics team: Show lost revenue from the website
</h2>
<br />

<p>At Buttercup Enterprises, I noticed we currently lack real-time visibility into lost revenue from our website. Our senior managers are keen on monitoring these revenue trends throughout the day using a dashboard.
</p> 

<p>So, my task is to create a Single Value visualization that displays lost revenue specifically from our company website and integrate it seamlessly into our dashboard.</p> 

<b>Steps:</b> 

<p>1. I navigated to Settings > Lookups within Splunk.</p>
<p align="center">
<img src="https://imgur.com/V9c2iH9.png" height="65%" width="65%" alt=""/>
</p>
<p>2. I clicked on Lookup table files to verify the presence of the ‘product_codes.csv’ file in my environment.</p>
<p align="center">
<img src="https://imgur.com/HoAm3ZI.png" height="65%" width="65%" alt=""/>
</p>

<p align="center">
<img src="https://imgur.com/HgT6enB.png" height="65%" width="65%" alt=""/>
</p>

<p>3. Returning to my app, I ensured I was in the Search view. To familiarise myself with the contents of the lookup file, I utilised the inputlookup command. This command allows me to view the fields and values contained within the file:

| inputlookup product_codes.csv

Reviewing the resulting table helped me understand the structure of the lookup file.
</p>


<p>4. After examining the lookup file, I proceeded to enhance my web server purchase events with additional data. Using the lookup command, I extracted the product_price field from the CSV file and integrated it into my search for events over the last 60 minutes:

index=main sourcetype=access_combined action=purchase
| lookup product_codes.csv product_id

Upon running this search, I observed the inclusion of the product_price field among the extracted fields on the left-hand side of the page, alongside new fields such as 'category' and 'product_name'. This data was facilitated by Splunk, leveraging the product_id field present in our data.
</p>

<p align="center">
<img src="https://imgur.com/TcXJqnP.png" height="65%" width="65%" alt=""/>
</p>

<p>5. Next, I customised my search criteria to focus specifically on failed purchase events. This refinement is crucial for measuring and calculating lost revenue. I applied a search filter to isolate events where the status code indicated an error (status >= 400):

index=main sourcetype=access_combined action=purchase status>=400
| lookup product_codes.csv product_id
</p>

<p align="center">
<img src="https://imgur.com/jLC8qZ0.png" height="65%" width="65%" alt=""/>
</p>

<p>6. Finally, to quantify the total amount of revenue lost due to these failed purchase events over time, I employed the timechart command with the sum function. This function calculates the sum of values in the specified field—in this case, product_price:

index=main sourcetype=access_combined action=purchase status>=400
| lookup product_codes.csv product_id
| timechart sum(product_price)


To present this data effectively, I switched to the Visualization tab if it wasn't already displayed and configured the visualisation to a Single Value format. I further enhanced the presentation by adjusting formatting options, including adding a currency symbol (£, $, or €) in the Number Format section to clearly indicate monetary values.

Once satisfied with the visualisation, I added it to my dashboard and titled the panel ‘Business Analytics - Lost Revenue’. This ensured that the dashboard provided a clear overview of the financial impact caused by failed purchase events, aiding in informed business decisions.
</p>

<p align="center">
<img src="https://imgur.com/hsL0rQQ.png" height="65%" width="65%" alt=""/>
</p>

<p align="center">
<img src="https://imgur.com/iz8DrL4.png" height="65%" width="65%" alt=""/>
</p>

<p align="center">
<img src="https://imgur.com/tB35yQe.png" height="65%" width="65%" alt=""/>
</p>


<h2>Part 5 – Security and Fraud teams: Show website activity by geographic location
</h2>
<br />

<p>I'm with Buttercup Enterprises, headquartered in the United States. We're concerned about potential fraudulent transactions originating from other countries, but right now, we lack visibility into the origins of our website traffic. To address this, we'll develop a Cluster Map visualization to pinpoint the geographic locations of all visitors connecting to our website.
</p> 

<b>Steps:</b> 

<p>1. Firstly, I conducted a search to gather all web server events using the iplocation and geostats commands to aggregate the events based on City. In our data, the 'City' field is automatically generated when we apply the iplocation command to the client IP addresses. Here's the Splunk query I used:

   index=main sourcetype=access_combined
   | iplocation clientip | geostats count by City

This query helps to visualise where our website traffic is originating from based on geographical locations.
</p>

<p align="center">
<img src="https://imgur.com/TTxvsau.png" height="65%" width="65%" alt=""/>
</p>

<p>2. If not already selected, I navigated to the Visualization tab. To present the data effectively, I chose the Cluster Map as the visualization type. This type of map displays the locations of our clients, which includes our customers connecting to the company's website.

After configuring the Cluster Map to display geographical data, I ensured to incorporate the resulting map into our dashboard. I labelled the panel with a descriptive title such as 'Security and Fraud - Customer Locations'. This addition enhances our dashboard with a clear visual representation of customer connections and their geographical distribution.
</p>

<p align="center">
<img src="https://imgur.com/gqbkU60.png" height="65%" width="65%" alt=""/>
</p>

<b>Bonus: removing events coming from “United States” from my map</b> 

<p>Description: The map I've generated shows customers from all countries. Since Buttercup Enterprises is a US-based company, I'm particularly interested in customers who are located outside the US. This will help our Security team focus on non-US customers for their analysis.
In the next task, I will explain how to remove events originating from the "United States" from the map.

| search Country!="United States": After determining the country using iplocation, the search command filters out events where the Country field is equal to "United States". This means it excludes events originating from the United States from further processing.

</p>

<p align="center">
<img src="https://imgur.com/Fq1UCk5.png" height="65%" width="65%" alt=""/>
</p>



<h2>Part 6 – Customise Your Dashboard
</h2>
<br />

<p>Description: Having a dashboard with multiple panels is powerful, but it's crucial to ensure that my dashboard layout is clear and easy for users to understand.

The Buttercup Enterprises Marketing team has reviewed what I've developed so far and has provided me with a custom background image they want incorporated into our new dashboard. In this exercise, I will upload the custom background image and reorganise the panels to align with the new design. Lastly, I'll configure each panel to use the global time picker to ensure it's all set for sharing with the business!
</p> 

<b>Steps:</b> 

<p>1. To add a custom background image to my dashboard, I navigated to the dashboard section by clicking on "Dashboards" in the top menu bar. From there, I selected my dashboard and entered edit mode by clicking "Edit".
</p>

<p align="center">
<img src="https://imgur.com/QaRMVV0.png" height="65%" width="65%" alt=""/>
</p>

<p>2. In edit mode, I located the Background Image section and pasted the URL of the custom image I wanted to use. After applying the image, I ensured it fit within the dashboard dimensions by selecting 'Contain' from the dropdown menu.
</p>

<p align="center">
<img src="https://imgur.com/02NAWHi.png" height="65%" width="65%" alt=""/>
</p>

<p>3. Next, I resized each dashboard panel to fit neatly within the areas defined by the custom background image. Once satisfied with the layout, I saved the changes.
</p>

<p align="center">
<img src="https://imgur.com/DJRRSnQ.png" height="65%" width="65%" alt=""/>
</p>

<p>4. To enhance the visual appeal, I adjusted the transparency of each panel except the Cluster Map visualisation. I accessed the Configuration panel, changed the background colour to transparent, and repeated this step for all relevant panels.
</p>

<p>5. Lastly, I linked all dashboard panels to the Global Time Picker for unified time control. In edit mode, I edited each panel's data source to use the Global Time Range ('global_time'), ensuring consistency across the dashboard. After applying these settings to each panel, I saved the dashboard and tested its functionality by adjusting the time range from the dropdown list.
</p>

<p>6. These streamlined steps ensure my dashboard not only looks visually appealing with a custom background but also functions efficiently with synchronised time controls across all panels.
</p>
<p align="center">
<img src="https://imgur.com/OcZGiXG.png" height="65%" width="65%" alt=""/>
</p>


<br />
<p>Through these exercises, I've improved data visibility and operational insights within Splunk for Buttercup Enterprises, enhancing decision-making across departments with custom apps, tailored dashboards, and targeted data visualisations.</p>


<h2>Languages Used</h2>

- <b>SPL (Search Processing Language): </b> Used extensively for querying and analysing data within Splunk. 
- <b>Regular Expressions (RegEx): </b> Employed for field extraction and pattern matching in data processing.

<h2>Tools and Environments Used </h2>

- <b>Splunk Enterprise: </b> Deployed as the primary platform for data collection, indexing, and analysis.
- <b>Dashboards and Visualizations with Simple XML: </b> Utilised for creating custom dashboards with visualisations such as Column Charts, Bar Charts, Area Charts, Single Value displays, and Cluster Maps.
- <b>Global Time Picker: </b> Integrated across dashboards to ensure unified time-based analysis and monitoring.
- <b>Custom Background Images: </b> Added to dashboards for visual enhancement and brand representation.
