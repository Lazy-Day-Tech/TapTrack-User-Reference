# Navigation
This document provides an overview of how navigation is implemented in the project using Jetpack Compose and the Navigation component.  
## Overview
The navigation in ComposeApp is managed using the NavHost and NavController from the Jetpack Navigation Compose library. The navigation graph is defined in the NavGraph.kt file, which sets up the different composable destinations and their respective routes.  
## Navigation Graph
The navigation graph is defined in the NavGraph composable function. This function sets up the navigation routes and the corresponding composable screens. Each screen is represented by a composable function, and the routes are defined as strings.  
### Setting Up Navigation
The NavGraph function is called in the MainActivity to set up the navigation when the app starts. The MainActivity initializes the NavController and NfcManager, and then calls the NavGraph function to set up the navigation graph.  
### Adding New Destinations
To add a new destination to the navigation graph, follow these steps:  
Create a new composable function for the screen.
Add a new composable entry in the NavGraph function with a unique route.

#### Example
```kt
composable("NewPage") { NewPage(navController) }
```

### Handling Navigation Arguments
Some destinations may require arguments to be passed. This can be done by defining the route with placeholders and retrieving the arguments in the composable function using the backStackEntry parameter. 

#### Example
```kt
composable("ReportLookupPage/{filterName}") { backStackEntry ->
            val filterName = backStackEntry.arguments?.getString("filterName")
            ReportLookupPage(navController, sharedViewModel, filterName, nfcManager) }
    }
```