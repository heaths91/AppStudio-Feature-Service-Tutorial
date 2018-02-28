# ESRI AppStudio Tutorial
# Adding REST services to your app
A quick guide on how to use QT and AppStudio and how to add a REST service to your app

### Prerequisites
1. Have/obtain an ESRI account
2. Download <a href="http://doc.arcgis.com/en/appstudio/download/" rel="nofollow">Esri AppStudio</a>

### Getting Started
After you have successfully installed Esri AppStudio you are now ready to create your app.
1. Open Esri AppStudio on your desktop/laptop computer
2. Click 'new app'
3. Select 'Hello World (runtime)'
4. Rename it something relevant to your project
5. Create

Once you have created your app, you can now test it by clicking 'Run'

## Changing your study area and embedding a REST service
You will now want to open your app in QT which was included in your AppStudio download package. To do this click the 'edit' button within App studio symbolized as {;}. You will now have access to the code and can begin editing. First, determine where you want your study area to be. For the purposes of this tutorial I chose Tacoma, Washington. Remember that this code is calling for map coordinates, the easiest way to determine these is to open your favorite GIS package and hover over the area you want to focus on and record the coordinates there. To change them within the code, navigate to this area of the code and change the x/y coordinates to your specific area.

         
       " Map{
            id:map

            BasemapTopographic{}
            initialViewpoint: ViewpointCenter {
                id: viewpoint
                // Specify the center Point
                center: Point {
                    x: -13635477
                    y: 5986422
                    spatialReference: SpatialReference { wkid: 102100 }
                }
                // Specify the scale
                targetScale: 1000000
            } "
            
Now after you have done this, make sure to file/saveall , now navigate back to AppStudio and select 'Run', and your app should look like this:
<img src="/heaths91/AppStudio-Feature-Service-Tutorial/blob/master/tacoma.png" alt="" style="max-width:100%;">

Are you still with me? I hope so, now that we have our study area defined we want to add our feature service. For the purposes of this tutorial I will be calling a REST service containing the hospitals in Washington. We can do that by adding this little chunk of code directly under the previous set we just played with.

           "FeatureLayer {
                ServiceFeatureTable {
                    url: "https://services6.arcgis.com/eIF8pWUENRGiMcYy/arcgis/rest/services/Hospitals/FeatureServer/0"
                }
            }"
Now if you go to file/saveall again, you can test your app and it should populate with your REST service!
<img src="/heaths91/AppStudio-Feature-Service-Tutorial/blob/master/featureservice.png" alt="" style="max-width:100%;">
            

### Author
Stuart Heath MSGT University of Washington-Tacoma

### Acknowledgement
This tutorial is based on information from <a href="https://developers.arcgis.com/qt/latest/qml/sample-code/sample-qt-featurelayer-featureservice.htm" rel="nofollow">ArcGIS for Developers</a>

### License
Copyright 2017 Esri
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
imitations under the License.
