# SPAPI
A Swift API for the Smart Parking API 

Currently depends on Alamofire. Was used in "Parkachu" by team Citnain for GovHack 2016.

Creating an API Object:
```swift
let spAPI = SPAPI(apiKey: "<apikey>", siteCode: "<sitecode>")
```
Use the API key and site code you were provided to initialize the API.

Getting all the lots:
```swift
spAPI.getAllLots({ lots, error in })
```
Lots is an ```[SPLot]?```, and error is an ```NSError?```. If the error is nil, then you will have some lots in the variable.

Getting the occupancy of an array of lots:
```swift
spAPI.getOccupanciesForLots(self.lots, callback: { newLots, error in })
```
The new lots are a similar data structure to above, but has ```updated``` available and ```taken``` properties.
