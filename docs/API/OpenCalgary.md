# OpenCalgary

```curl
curl --location 'https://data.calgary.ca/resource/5fdg-ifgr.json?station_number=05BH004&%24order=timestamp%20DESC&%24limit=1'
```

## fetchStationData

Fetches the latest station data from the Calgary data API.

### Parameters
- `stationNumber` (optional): The station number to fetch data for. Defaults to `05BH004`.

### Returns
- `List<RiverData>`: A list of river data objects.

### Exceptions
- Throws `ApiException` if the API call fails.
