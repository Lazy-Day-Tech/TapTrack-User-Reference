# OpenCalgary


## fetchStationData

Fetches the latest station data from the Calgary data API.

### Parameters
- `stationNumber` (optional): The station number to fetch data for. Defaults to `05BH004`.

### Returns
- `List<RiverData>`: A list of river data objects.

### Exceptions
- Throws `ApiException` if the API call fails.
