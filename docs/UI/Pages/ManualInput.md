# ManualInput
Allows for a manual method of finding booking records

## Filters

Several filters are defined to filter the booking records based on their status, date, and type:
- `filterNotCheckedIn`: Filter for records that are not checked in.
- `filterCheckedIn`: Filter for records that are checked in.
- `filterReturned`: Filter for records that are returned.
- `filterToday`: Filter for records for today.
- `filterTomorrow`: Filter for records for tomorrow.
- `filterCustom`: Filter for custom date ranges.
- `filterType4`, `filterType6`, `filterType8`, `filterType10`, `filterType12`:
Filters for different types of rafts.
- `filterTypeBowYak`, `filterTypeKayak` (Includes both solo and dual), `filterTypeLifeJacket`: Filters for different types of equipment.
> The ManualInput page doesnt currently support a date picker, and only supports `Today` or `Yesterday`

## UI Components
- **Search Bar**: Provides a search bar for filtering booking records by search query.
- **Dropdown Menus**: Provides dropdown menus for filtering records by status, date, and type.
- **Refresh Button**: Provides a button to refresh the booking records.
- **Booking List**: Displays a list of filtered booking records.

