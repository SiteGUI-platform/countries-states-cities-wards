# countries-states-cities-wards
Inaccurate addresses entered by your customers cost your online store money (as packages to wrong addresses cannot be delivered and must be returned). This repo aims to be the most accurate source for all countries in the world and provide accurate country, state, city and ward/zip/postal code through a simple lookup to an edge CDN server near the users. The ward information can be changed to postal/zip code by changing the ward to zip/postal code in the JSON files. 

The initial database is taken from https://github.com/dr5hn/countries-states-cities-database. Our approach is to separate each country into its own folder (country's ISO short name) which contains an index.json file to list all of its states. Each state has a state ID and a state_id.json file containing all of its cities and wards/zip/postal codes (if available). On a page where the script is deployed, when the user selects a country, the index.json for that country gets loaded and states are displayed. When the user selects a state, the state_id.json file is loaded and cities and wards/zip/postal codes (if enabled and available) are displayed to the user for selection. This approach ensures the loading is fast and if there are changes to the countries' data, changes can be updated and reviewed easily.

Demo https://sitegui-platform.github.io/countries-states-cities-wards/demo.html

How to use?

Include the following script in your page:

```<script src="https://sitegui-platform.github.io/countries-states-cities-wards/sgaddress.js?v=15" id="sg-js-address" data-source="https://raw.githubusercontent.com/SiteGUI-platform/countries-states-cities-wards/main/"></script>```

Add a wrapper around your address input fields and change data-selector-* to relevant input's ID/class (CSS selector). Enable data-addr-add to allow adding non-existing value to the inputs and specify data-selector-street2 to allow ward/district selection.

```<div class="sg-js-address" data-addr-add="1" data-default-country="US" data-selector-country="select.billing-country" data-selector-state=".sg-address-state" data-selector-zip=".sg-address-zip" data-selector-city=".sg-address-city-input" data-selector-street2=".sg-address-street2">```

Feel free to fork and maintain your own country databases (remember to update "data-source" to point to your source). However, if the country databases here are outdated or inaccurate, we'd appreciate if you can make a pull request to update them here to share it with other people. 
