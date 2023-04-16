# Using Google Maps API

- Get longitude and latitude for the address
    - on the google sheet, we select the “Extensions” and then select the “App Script”
    - we will replace the default code with this code:
    
    ```jsx
    function geocodeAddress() {
        let sheet = SpreadsheetApp.getActiveSheet();
        let rows = sheet.getDataRange().getValues();
        const geocoder = Maps.newGeocoder();
        sheet.getRange(1, 7).setValue("Latitude").setFontWeight("bold");
        sheet.getRange(1, 8).setValue("Longitude").setFontWeight("bold");

        for (let i = 1; i < rows.length; i++) {
            let row = rows[i];
            const address = row[0] + ", " + row[1] + ", " + row[2] + ", " + row[3];
            let response = geocoder.geocode(address);
            if (response.status == 'OK') {
                let location = response.results[0].geometry.location;
                sheet.getRange(i+1, 7).setValue(location.lat);
                sheet.getRange(i+1, 8).setValue(location.lng);
            }
      }
    }
    ```
    
    - we will rename the project into any name you want and then save the project
    
    ![Screenshot 2023-03-26 at 10.44.38 PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cfb8dafa-d626-428f-b999-c64e01455c9b/Screenshot_2023-03-26_at_10.44.38_PM.png)
    
    - we can now run the project, however we will faced some authentication problem
    - at first, we will need to preview permission
    
    ![Screenshot 2023-03-26 at 11.08.49 PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/74a37adc-3528-4476-904c-625056fed9cc/Screenshot_2023-03-26_at_11.08.49_PM.png)
    
    - then choose an account that has the GCP free tier
    
    ![Screenshot 2023-03-26 at 11.08.57 PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/47bfccfe-66ee-4980-91ac-1f8a40574310/Screenshot_2023-03-26_at_11.08.57_PM.png)
    
    - just click “Advanced” at the left - centre side
    
    ![Screenshot 2023-03-26 at 11.09.06 PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8804bf48-3e21-4c6d-a125-5ceec1c5fc04/Screenshot_2023-03-26_at_11.09.06_PM.png)
    
    - then just click the “Go to test_run (unsafe)” at bottom left side, then it should be able to run and produce the execution log
    
    ![Screenshot 2023-03-26 at 11.15.13 PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0351525d-0153-44c5-91b3-ea88f97be66d/Screenshot_2023-03-26_at_11.15.13_PM.png)
    
    - actually, we can click the Executions at the side bar and check whether the code is being complete run or not
    - after that, we should able to get the latitude and longitude inside our google sheet
    - 
- Enable the Maps API, Google Sheet API and Geocoding API
    - open the google console, create a new project and rename it as any name your want
    - go to the navigation menu, select “APIs & Services” , then select “Library”, then find “Google Maps API” and “Google Sheet API”, then enable them.
    - go to the Google Map API, create the API key, then save it in somewhere else
    - 
- Code for Google map embed and Geolocation
    - we are now leave a space with the “spacer” and then we put a header with name “My location” and make a division with the id “map”
    - replace the API keys with the google map api keys that you had created just now
    - replace the javascript file with your javascript file
    
    ```html
    <hr class="spacer">
    	 <div id="map">
              <h1> My Location </h1>
    						<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEYS_&callback=initMap"
                async defer></script>
                <script async defer src="https://apis.google.com/js/api.js" onload="gapiLoaded()"></script>
                <script async defer src="https://accounts.google.com/gsi/client" onload="gisLoaded()"></script>
                <script src="any_name_you_put_in_your_javascript_file.js" ></script>
    	</div>
    ```
    
- go to the Google Sheet API, create the API keys and client ID , then replace them in the code
- go to your google sheet, go to the “Share” , change the general access to “ anyone with the link” and “viewer”, so that it is in public

    > **Note**
    > <br>⚠️ [https://docs.google.com/spreadsheets/d/1FX1WXBFKnCWf6O2pVTWwvxw53XrvWrQ_3Khpu8p8SYg/edit#gid=0](https://docs.google.com/spreadsheets/d/1FX1WXBFKnCWf6O2pVTWwvxw53XrvWrQ_3Khpu8p8SYg/edit#gid=0)
    
- above show the link for the google sheet, we just copy the yellow highlighted part as this will be our google sheetID and we will replace it in the code
- for the range in the GetSheetData(), we replace the range that have our data to be shown
    
    ```js
    // Load the API client library
    // gapi.load('map', initMap);

    function gapiLoaded() {
        gapi.load("client", sheet_api);
        gapi.load(
        "map",
        (initMap = function () {
            // Create a new map object centered on a specific location
            var map = new google.maps.Map(document.getElementById("map"), {
            center: { lat: 6.1224889, lng: 100.3528662 },
            zoom: 8,
            });
        })
        );
    }

    function gisLoaded() {
        tokenClient = google.accounts.oauth2.initTokenClient({
        client_id:
            "YOUR_CLIENT_ID",
        scope: "https://www.googleapis.com/auth/spreadsheets.readonly",
        callback: "", // defined later
        });
    }

    // Load the API client library
    async function sheet_api() {
        // Initialize the Google Sheets API client
        await gapi.client
        .init({
            apiKey: "YOUR_API_KEY", // Replace with your API key
            discoveryDocs: [
            "https://sheets.googleapis.com/$discovery/rest?version=v4",
            ],
        })
        .then(
            function () {
            getSheetData();
            },
            function (error) {
            // Handle any errors
            console.error(error.result.error.message);
            }
        );
    }

    // Retrieve latitude, longitude, and address data from a Google Sheet
    async function getSheetData() {
        //console.log("hhhhhhhhh");
        var sheetId = "YOUR_SHEET_ID"; // Replace with your Google Sheet ID
        var range = "Sheet1!D1:I"; // Replace with the range of cells containing your data
        var values = [];

        // Call the Google Sheets API to retrieve data

        gapi.client.sheets.spreadsheets.values
        .get({
            spreadsheetId: sheetId,
            range: range,
        })
        .then(
            function (response) {
            // Process the response data
            console.log(response);
            var rows = response.result.values;
            for (var i = 1; i < rows.length; i++) {
                var row = rows[i];
                console.log(row);
                var lat = parseFloat(row[3]);
                console.log(row[3]);
                var lng = parseFloat(row[4]);
                console.log(row[4]);
                var address = row[0];

                // Store the latitude, longitude, and address in an array
                values.push({
                address: address,
                latitude: lat,
                longitude: lng,
                });
            }
            console.log(values);
            // Create a new Google Map centered on the first marker
            var center = new google.maps.LatLng(
                values[0].latitude,
                values[0].longitude
            );
            var mapOptions = {
                zoom: 8,
                center: center,
            };
            var map = new google.maps.Map(
                document.getElementById("map"),
                mapOptions
            );

            // Add a marker for each latitude/longitude pair
            for (let i = 0; i < values.length; i++) {
                let latLng = new google.maps.LatLng(
                values[i].latitude,
                values[i].longitude
                );
                let marker = new google.maps.Marker({
                position: latLng,
                map: map,
                title: values[i].address,
                });

                // Add an info window to the marker that shows the corresponding address

                //console.log(values[i].address);
                let infoWindow = new google.maps.InfoWindow({
                content: values[i].address,
                });
                marker.addListener("click", function () {
                console.log(infoWindow);
                if (!marker.open) {
                    infoWindow.open({ anchor: marker, map });
                    marker.open = true;
                } else if (marker.open) {
                    infoWindow.close();
                    marker.open = false;
                }
                });
            }
            },
            function (error) {
            // Handle any errors
            console.error(error.result.error.message);
            }
        );
    }
    ```
    
now that, we can adjust the height and weight of the map
    
```css
#map {
    height: 400px;
    width: 800px; 
}
```
    
On the live server and test the website

* make sure the install the “live server” extension in VS code
* on the bottom right, there is a “live server” , you just click on it to open the website