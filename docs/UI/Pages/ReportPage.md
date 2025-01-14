# Report Page

## Overview

The ReportPage component aggregates and displays the following:
- Booking Statistics: Shows the number of bookings for the day, average float time, and counts of checked-in, not-checked-in, and returned rentals.
- River Level Widget: Displays the current river water level.
- Pie Charts: Visualizes raft rental data based on status (Checked-In, Not Checked-In, Returned) and raft type (4-Man, 6-Man, etc.).
- Interactive Controls: Provides buttons to toggle between viewing different pie charts (status vs. type) and an informational button that shows a note from the developer regarding graph behavior.

### Key Features
- Data Fetching: Fetches data about today's bookings and river data asynchronously.
- Pie Charts: Interactive charts showing different metrics with the ability to toggle between "Status" and "Type" charts.
- Loading Indicators: Displays a loading spinner while data is being fetched.

## Code Breakdown
### Composables Used
- ReportPage Composable
    - The main composable responsible for the layout and data flow of the report page. It structures the UI by combining different sections and handling the asynchronous data fetching.

- State Management
    - The page uses several state variables to manage the UI's dynamic elements, such as the loading state, selected chart type (status or type), and river data. These states allow the page to respond to user interactions and update as data is fetched.

- Data Fetching
    - The page uses an effect to fetch river data and rafting bookings when the page is first displayed. This process runs asynchronously, ensuring that the page can load data without blocking the UI.

- Layout
    - The page is organized using a combination of rows and columns:
        - The top section includes a back navigation button and a river level widget.
        The main section displays booking metrics, charts, and buttons for toggling between different data visualizations.

- Booking Metrics Widgets
    - The page displays various metrics related to bookings, such as:
        - The total number of bookings for the day.
        - The average float time for the day.
        - The number of checked-in, not-checked-in, and returned rentals.

- Pie Charts
    - The page includes two sets of pie charts:
        - Raft Status: Displays data based on whether the rafts are checked-in, not checked-in, or returned.
        - Raft Type: Displays data based on the type of raft rented, such as 4-person, 6-person, and other categories.

- Interactive Chips
    - Two interactive chips allow the user to toggle between the "Status" chart and the "Type" chart.
    - An additional button lets the user toggle an informational note from the developer.

### Data Handling

- Fetching Bookings
    - The app retrieves today's rafting bookings, filtering the data based on the current day to ensure that only relevant bookings are shown.

- River Data
    - The page fetches the current river level, which is displayed at the top of the screen.

- Average Float Time
    - The app calculates the average float time for today's bookings, which helps to understand how long rafts are typically out on the water.

- Rental Counts by Status and Type
    - The page calculates the number of rentals based on their status (Checked-In, Not Checked-In, Returned) and type (e.g., 4-person raft, 6-person raft, etc.).

### UI Components
- RiverLevelWidget: Displays the current river water level.
- BigWidget: Displays large metrics like the total number of bookings.
- WideWidget: Displays metrics with a wider layout, such as the average float time.
- BasicReportWidget: Displays individual booking statistics such as checked-in, not-checked-in, and returned rentals.
- PieChart: Displays data in a circular graph format to visualize the status and type of rentals.
- Chip: Provides a toggle button to switch between different pie chart views.
- OutlinedButton: Displays a button to toggle an informational note from the developer.
- ErrorDialogue: Displays a modal dialog containing a note from the developer, informing users about the experimental nature of the graphing feature.

### Error Handling
- Loading State: While data is being fetched, a loading spinner is displayed to inform the user that the page is processing and loading the necessary information.
- Graph Note: An informational note from the developer is displayed to explain that the graphing feature is still in development and may behave unexpectedly on some devices.

