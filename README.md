___

<h1 align="center"> :warning:  THIS IS THE DEV BRANCH!  :warning:</h1>
<h2 align="center">
May contain bugs, broken features, and should generally be avoided.</br></br>Master branch is located here:</br> https://github.com/custom-components/sensor.radarr_upcoming_media</h2>


___


# Radarr Upcoming Media Component

Home Assistant component to feed [Upcoming Media Card](https://github.com/custom-cards/upcoming-media-card) with
Radarr's upcoming releases.</br>
This component does not require, nor conflict with, the default Radarr component.</br></br>
<link href="https://fonts.googleapis.com/css?family=Lato&subset=latin,latin-ext" rel="stylesheet"><a class="bmc-button" target="_blank" href="https://www.buymeacoffee.com/FgwNR2l"><img src="https://www.buymeacoffee.com/assets/img/BMC-btn-logo.svg" alt="Buy me a coffee"><span style="margin-left:5px">If you feel I deserve it, you can buy me a coffee</span></a></br>
</br>
<a href="https://www.themoviedb.org/"><img width="200" src="https://www.themoviedb.org/assets/1/v4/logos/408x161-powered-by-rectangle-green-bb4301c10ddc749b4e79463811a68afebeae66ef43d17bcfd8ff0e60ded7ce99.png">
</br>This product uses the TMDb API but is not endorsed or certified by TMDb.</a>

## Installation:

1. Install this component by copying to your `/custom_components/sensor/` folder.
2. Add the code to your `configuration.yaml` using the config options below example. 
3. **You will need to restart for the component to start working.**

### Options

| key | default | required | description
| --- | --- | --- | ---
| api_key | | yes | Your Radarr API key
| host | localhost | no | The host Radarr is running on.
| port | 7878 | no | The port Radarr is running on.
| urlbase | / | no | The base URL Radarr is running under.
| days | 60 | no | How many days to look ahead for the upcoming sensor.
| ssl | false | no | Whether or not to use SSL for Radarr.
| theaters | true | no | Show or hide theater releases.
| max | 5 | no | Max number of items in sensor.

### Sample config:

```
sensor:
- platform: radarr_upcoming_media
  api_key: YOUR_API_KEY
  host: 192.168.1.4
  port: 7878
  days: 120
  ssl: true
  theaters: false
  max: 10
```

### Card Content Defaults

| key | default | example |
| --- | --- | --- |
| title | $title | "Night of the Living Dead" |
| line1 | $release | "In Theaters Mon, 10/31" if it's a theater release and more than a week away or "Available Monday" if it's a physical release and within a week.|
| line2 | $genres | "Action, Adventure, Comedy" |
| line3 | $rating - $runtime | "★ 9.8 - 01:30"
| line4 | $studio | "Laurel Group Inc."
| icon | mdi:arrow-down-bold | https://materialdesignicons.com/icon/arrow-down-bold
