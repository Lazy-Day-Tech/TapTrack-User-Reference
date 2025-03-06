# ManualInput

The code imports various components from Jetpack Compose, Kotlinx DateTime, and other libraries to manage UI components, state, navigation, and logging.
Composable Function: ManualInputV2

- **Description:** This function provides a UI for manual input, displaying a list of bookings with various filters.
    - **Parameters:**
        - `navController`: Optional navigation controller for navigating between different pages.
        - `nfcManager`: Manager for handling NFC-related operations.
        source: Optional string to identify the source page.

## Variables
- `bookingItems`: State to hold the list of booking records.
- `sourcePage`: State to hold the source page information.
- `searchQuery`: State to hold the search query text.
- `safePadding`: State to hold safe padding values.
- `scope`: Coroutine scope for launching coroutines.
- `selectedRecord`: State to hold the currently selected booking record.
- `isRefresh`: State to indicate if the data should be refreshed.
- `isLoading`: State to indicate if data is being loaded.

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

## Functions
- `LaunchedEffect`: Fetches booking records when the component is first launched and when isRefresh is triggered.
- `applyFiltersAndSearch`: Applies the defined filters and search query to the booking records and returns the filtered list.

## BookingRecordView

- Displays a detailed view of the selected booking record with options to check in or check out.
ErrorDialogue

- Displays an error dialogue if the custom date filtering feature is not available.
StandardCircularProgressIndicator

- Displays a loading indicator while booking records are being fetched.