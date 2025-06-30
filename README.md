# MMM-TheSpaceDevs

This is a module for [MagicMirror²](https://github.com/MagicMirrorOrg/MagicMirror/).

This module will show you upcoming rocket launches based on [TheSpaceDevs](https://thespacedevs.com/) API.
Unauthenticated users have access to 15 api calls per hour.

## Installation

1. Navigate to your MagicMirror's modules folder, and run the following command: `git clone https://github.com/AlexMNet/MMM-TheSpaceDevs`
2. Add the module and a valid configuration to your `config/config.js` file

## Using the module

This is an example configuration for your `config/config.js` file:

```js
let config = {
  modules: [
    // TABLE VIEW CONFIG
    {
      module: 'MMM-TheSpaceDevs',
      position: 'bottom_right',
      config: {
        updateInterval: (60 * 60 * 1000) / 15,
        records: 5,
        type: 'table',
        locationIds: [11],
        headerText: 'Vandenberg Space Force Base - Launches',
        timeZone: 'America/New_York'
      },
    },
    // DETAIL VIEW CONFIG
    {
      module: 'MMM-TheSpaceDevs',
      position: 'middle_center',
      config: {
        updateInterval: (60 * 60 * 1000) / 15,
        type: 'detail',
        locationIds: [11],
        width: 500,
      },
    },
  ],
};
```

## Configuration options (all are optional see MMM-TheSpaceDevs.js for defaults)

| Option           | Description                                                                                                                                 |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `records`        | # of launches you want returned from the api for table view. Between 1 - 7 looks best                                                       |
| `updateInterval` | How often you want to fetch data from the API in ms. Default is 15 times per hour                                                           |
| `apiKey`         | Add apiKey for increased API rate limits visit [TheSpaceDevs](https://ll.thespacedevs.com/docs/#/launch/launch_upcoming_list) for more info |
| `type`           | Template to view. "detail" or "table"                                                                                                       |
| `locationIds`    | An array of locationId integers you want data from. If no location is provided you will recieve launch data from all locations              |
| `headerText`     | Text you want to add to your header for table view                                                                                          |
| `width`          | Width is used for the detail template.                                                                                                      |
| `timeZone`       | Time zone for all displayed times.                                                                                                    |

## Important

1. TheSpaceDevs API is free to use but capped at 15 api calls per hour for unauthenticated users. This is important if you want to add both the detail view and table view to your magic mirror. Each module will make its own API call so set your updateIntervals accordingly. The default for this module is 15 api calls per hour which assumes you will only be using the table or detail view.

## Screenshot

Table View: Looks best in any of the corners.
![alt text](https://github.com/AlexMNet/MMM-TheSpaceDevs/blob/main/table_view.png?raw=true)

Detail View: Intended to be used for middle_center
![alt text](https://github.com/AlexMNet/MMM-TheSpaceDevs/blob/main/detail_view.png?raw=true)

## Location IDs

| Location ID  | Name                                                                                                                                             |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------|
| 155          | White Sands Missile Range                                                                                                                        |
| 7            | Sohae Satellite Launching Station,  Cholsan County, North Pyongan Province, Democratic People's Republic of Korea                                |
| 18           | Vostochny Cosmodrome, Siberia, Russian Federation                                                                                                |
| 159          | Sutherland Spaceport, United Kingdom                                                                                                             |
| 26           | Tanegashima Space Center, Japan                                                                                                                  |
| 145          | Shahrud Missile Test Site, Islamic Republic of Iran                                                                                              |
| 12           | Cape Canaveral SFS, FL, USA                                                                                                                      |
| 20           | Air launch to orbit                                                                                                                              |
| 177          | Apollo crater, Moon                                                                                                                              |
| 19           | Taiyuan Satellite Launch Center, People's Republic of China                                                                                      |
| 13           | Guiana Space Centre, French Guiana                                                                                                               |
| 168          | Oceanus Procellarum, Moon                                                                                                                        |
| 31           | Spaceport America, NM, USA                                                                                                                       |
| 27           | Kennedy Space Center, FL, USA                                                                                                                    |
| 151          | Broglio Space Center, Kenya                                                                                                                      |
| 144          | Air launch to Suborbital flight                                                                                                                  |
| 164          | Koonibba Test Range, South Australia                                                                                                             |
| 160          | Arnhem Space Centre, Australia                                                                                                                   |
| 163          | El Arenosillo Test Centre, Spain                                                                                                                 |
| 179          | Atlas crater, Moon                                                                                                                               |
| 166          | Spaceport Kii, Japan                                                                                                                             |
| 10           | Rocket Lab Launch Complex 1, Mahia Peninsula, New Zealand                                                                                        |
| 25           | Pacific Spaceport Complex, Alaska, USA                                                                                                           |
| 157          | SaxaVord Spaceport, United Kingdom                                                                                                               |
| 162          | Edwards Air Force Base, USA                                                                                                                      |
| 3            | Sea Launch                                                                                                                                       |
| 156          | Whalers Way Orbital Launch Complex, South Australia                                                                                              |
| 17           | Jiuquan Satellite Launch Center, People's Republic of China                                                                                      |
| 181          | Bowen Orbital Spaceport, Australia                                                                                                               | 
| 167          | Mare Tranquillitatis, Moon                                                                                                                       |
| 24           | Uchinoura Space Center, Japan                                                                                                                    |
| 171          | Descartes Highlands, Moon                                                                                                                        |
| 183          | Mons Mouton, Moon                                                                                                                                |
| 150          | Alcântara Space Center, Federative Republic of Brazil                                                                                            |
| 173          | Mare Fecunditatis, Moon                                                                                                                          | 
| 2            | Semnan Space Center, Islamic Republic of Iran                                                                                                    |
| 152          | RAAF Woomera Range Complex, Australia                                                                                                            |
| 11           | Vandenberg SFB, CA, USA                                                                                                                          | 
| 32           | Hokkaido Spaceport, Japan                                                                                                                        |
| 161          | Andøya Spaceport, Norway                                                                                                                         |
| 143          | SpaceX Starbase, TX, USA                                                                                                                         |
| 174          | Terra Apollonius, Moon                                                                                                                           |
| 1            | Pacific Missile Range Facility, Barking Sands, HI, USA                                                                                           |
| 147          | Interarmy Special Vehicles Test Centre, French Algeria                                                                                           |
| 6            | Plesetsk Cosmodrome, Russian Federation                                                                                                          |
| 169          | Fra Mauro Formation, Moon                                                                                                                        |
| 175          | Mare Crisium, Moon                                                                                                                               |
| 8            | Wenchang Space Launch Site, People's Republic of China                                                                                           |
| 29           | Corn Ranch, Van Horn, TX, USA                                                                                                                    |
| 180          | Mare Frigoris, Moon                                                                                                                              |
| 4            | Palmachim Airbase, State of Israel                                                                                                               |
| 9            | Naro Space Center, South Korea                                                                                                                   |
| 21           | Wallops Flight Facility, Virginia, USA                                                                                                           |
| 14           | Satish Dhawan Space Centre, India                                                                                                                |
| 153          | Tonghae Satellite Launching Ground, Democratic People's Republic of Korea                                                                        |
| 170          | Hadley–Apennine, Moon                                                                                                                            |
| 176          | Mons Rümker, Moon                                                                                                                                |
| 182          | Malapert-A, Moon                                                                                                                                 |
| 30           | Kapustin Yar, Russian Federation                                                                                                                 |
| 172          | Taurus–Littrow, Moon                                                                                                                             |
| 178          | Esrange Space Center, Sweden                                                                                                                     |
| 16           | Xichang Satellite Launch Center, People's Republic of China                                                                                      |
| 15           | Baikonur Cosmodrome, Republic of Kazakhstan                                                                                                      |
| 142          | Ronald Reagan Ballistic Missile Defense Test Site, Kwajalein Atoll, Marshall Islands                                                             |
| 5            | Dombarovskiy, Russian Federation                                                                                                                 |
| 146          | Svobodny Cosmodrome, Russian Federation                                                                                                          |
