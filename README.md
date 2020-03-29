# Spatial data 

Documentation 
GIS SETUP MANUAL
Author: Sabrina Lamie Awuni

Contents
•	Requirements
•	PostgreSQL setup
•	PostGIS setup
-Creating a spatial database manually
-Importing the shapefile
•	GeoServer setup
-Connecting GeoServer to PostGIS
•	Ngrok setup
-Connecting ngrok to user account




Requirements
•	PostgreSQL:
-Tested on PostgreSQL 9.6

•	PostGIS:
-Tested on PostGIS 2.5.3

•	GeoServer:
-Tested on GeoServer 2.16.2

Fundamental Assumption
Windows OS 64bit

PostgreSQL
1.	Install PostgreSQL
2.	Restart your computer
3.	Open PgAdmin 4
4.	Double click on PostgreSQL under servers and enter your password to connect


PostGIS
There are two methods of installing postgis:
•	Using the Stack Builder:*- Requires internet *
•	Using the offline installer:*- Does not require internet *

Installation using the Stack Builder
1.	Go to the start menu, look for Application Stack Builder , and open it.
2.	Select your Postgres instance and click next.
3.	Look among the extensions for PostGIS and select the x64 version.
4.	Install.
5.	Use postgres and your PostgreSQL password when it requests for the username
6.	and password for your PostgreSQL server.
7.	Check the create a spatial database option so that it sets up a spatial database
8.	for you. Note the name of the spatial database that is created.

Installation using the offline installer
1.	Obtain a copy of postgis-bundle-pg94x64-setup-2.5.1-1.exe
2.	Install.
3.	Use postgres and your PostgreSQL password when it requests for the username
4.	and password for your PostgreSQL server.
5.	You may check the create a spatial database option so that it sets up a spatial
6.	database for you. Note the name of the spatial database that is created.


Creating a spatial database
1.	Go to your start menu, look for pgAdmin 4 and open it.
2.	Connect to your server.
3.	Right click on databases and choose New Database.
4.	Supply a database name and click ok.
5.	Double click on the database you created.
6.	Right click on extensions and choose New Extension
7.	Scroll through the dropdown, look for postgis, and select it.
8.	Click ok to add the extension.
9.	Right click on extensions and choose New Extension
10.	Scroll through the dropdown, look for postgis, and select it.
11.	Click ok to add the extension.


Importing the shape file
1.	Obtain a copy of shapefiles.zip .
2.	Extract the archive.
3.	Go to your start menu, look for PostGIS 2.0 Shapefile and DBF Loader Exporter
4.	and open it
5.	Click View connection details and enter the
a.	username = postgres
b.	password = your PostgreSQL password
c.	database = the name of the spatial database you created. You can also use the one you created during the PostGIS installation if you did create one.
6.	Click ok.
7.	Click Add file and browse to the folder where you extracted the archive.
8.	Select the .shp files and click ok.
9.	Change the SRID to a desired value (eg. 26976).

GeoServer
1.	Install GeoServer.
2.	You may want to change the port number for the server from 8080 to 8090 or 1024 or something else which has not been allocated to another program because the oracle
3.	web administration service uses port 8080 .
4.	When the installation is complete go to your start menu, look for Start GeoServer
5.	and open it. Give it a little time to start up completely.
6.	Go to your start menu, look for GeoServer Web Admin Page and open it.
7.	The Geoserver Admin page should open up.
8.	Enter the geoserver credentials to login. The defaults are
9.	username = admin
10.	passowrd = geoserver

Connecting GeoServer to PostGIS
1.	Start GeoServer if you have not done that already. (Intructions are in previous section)
2.	Go to your start menu, look for GeoServer Web Admin Page and open it. The
3.	Geoserver Admin page should open up in your browser.
4.	Enter the geoserver credentials to login. The defaults are
5.	username = admin
6.	passowrd = geoserver
7.	Click on Workspaces in the sidebar on the left side.
8.	click on Add a new workspace
9.	Supply a name for the workspace.
10.	For the URI can just append the name of the workspace to
11.	localhost:PORT/geoserver/ where the PORT is the port number for your
12.	geoserver. You can look in the address bar of your browser if you have forgotten.
13.	Submit.
14.	Click Stores in the sidebar on the left side.
15.	Click Add a new store and choose PostGIS.
16.	Supply the values for the following fields.
17.	Workspace = The workspace you created earlier.
18.	Data source name = Enter a name for your data source here.
19.	Database = The name of the spatial database that you created.
20.	User = Your PostgreSQL username ( postgres ).
21.	Passwd = Your PostgreSQL password.
22.	Save.
23.	Click Layers in the sidebar on the left side.
24.	Click Add a new layer and choose the data store you created under Add layer from
25.	Click publish .
26.	Under Bounding boxes click on Compute from data and under Lat/Lon bounding box
27.	click on Compute from native bounds
28.	Save.
29.	Click Layer preview in the sidebar on the left
30.	Look for the layer that you created and choose PNG under select one to display a
31.	picture of the map.
32.	You could also click Open layers to get an interactive map.

Ngrok Setup and Connections.
1.	Sign up for ngrok on www.ngrok.com
2.	After creating an account download and install ngrok setup
3.	Run its set up, this will open the terminal
4.	Connect it to you account by copying your link from the site
5.	After, type in ngrok http 8080 on the terminal
6.	This will then open up your ngrok and show the status of your tunnel whether online or not(note that you will need internet connection and ensure your geoserver is running)
7.	The terminal will display your unique tunnel url which you can load and display your map.
8.	Copy this url and include it in your android and html code.




