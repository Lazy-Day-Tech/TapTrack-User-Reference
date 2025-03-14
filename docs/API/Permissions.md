# **User Permissions**

The system uses the Role-Based Access Control (RBAC) model to manage user permissions. Roles are created, removed, assigned, and modified with different permissions live. Changes will reflect within the application the next time the application is launched for the assigned user without needing to modify the codebase itself.

### Available Roles

- `Receptionist`
- `Manager`
- `Director`

### Permissions

The following permissions can be assigned to roles:

| **Permission Name**        | **Description**                                                                                          |
| -------------------------- | -------------------------------------------------------------------------------------------------------- |
| `checkin.perform`          | Perform customer check-in workflow                                                                       |
| `checkout.perform`         | Perform customer check-out workflow                                                                      |
| `shuttle.perform`          | Perform shuttle operations                                                                               |
| `booking.notes.modify`     | Modify booking notes                                                                                     |
| `booking.notes.view`       | View booking notes                                                                                       |
| `booking.flags.modify`     | Modify booking flags                                                                                     |
| `booking.flags.view`       | View flags                                                                                               |
| `booking.override` | Override booking states |
| `repair.create`            | Create a repair record                                                                                   |
| `repair.view`              | View repair records                                                                                      |
| `repair.notes.modify`      | Modify repair notes                                                                                      |
| `repair.notes.view`        | View Repair Notes                                                                                        |
| `repair.status.modify`     | Modify repair status                                                                                     |
| `repair.assigned.modify`   | Assign repair records to other users                                                                     |
| `repair.delete`            | Delete a repair record                                                                                   |
| `customer.view_full`       | View full customer information (First Name, Last Name, Waiver Names, Waiver Count, Phone Number, startTime, endTime, Float Time, BookingDateTime, Status, Rentals) |
| `customer.view_limited`    | View limited customer information (Last Name, Waiver Count, BookingDateTime, Status, Rentals)            |
| `customer.view_checked_by` | View who checked in and checked out a customer                                                           |
| `manualinput.perform`     | Perform manual input lookups                                                                             |
| `qr.perform`                  | Scan QR codes                                                                                       |
| `reports.view`             | Access reports                                                                                           |
| `repair.user.view` | View which users create/resolve repair records |
| `repair.update` | Update repair records |
|  `shuttle.reports` | View reports in Shuttle Management module | 
| `reports.floattime.view` | View advanced floattime information within the reporting module. Requires additional API call to calculate |

### Role-to-Permission Mapping

The following table maps roles to permissions:

> Subject to frequent modifications. List may not be up to date, check backend role values for more information.

| **Permission**             | **Receptionist** | **Manager** | **Director** |
| -------------------------- | :----------------: | :------------: | :----------:  |
| `checkin.perform`          | ✅                  | ✅             | ✅           |
| `checkout.perform`         | ✅                  | ✅             | ✅           |
| `shuttle.perform`          | ✅                  | ✅             | ✅           |
| `booking.notes.modify`     | ✅                  | ❌             | ✅           |
| `booking.notes.view`       | ✅                  | ✅             | ✅           |
| `booking.flags.modify`     | ✅                  | ❌             | ✅           |
| `booking.flags.view`       | ✅                  | ✅             | ✅           |
| `booking.override`         | ✅                  | ❌             | ✅           |
| `repair.create`            | ❌                  | ❌             | ✅           |
| `repair.view`              | ❌                  | ❌             | ✅           |
| `repair.notes.modify`      | ❌                  | ❌             | ✅           |
| `repair.notes.view`        | ❌                  | ❌             | ✅           |
| `repair.status.modify`     | ❌                  | ❌             | ✅           |
| `repair.assigned.modify`   | ❌                  | ❌             | ✅           |
| `repair.assignable`        | ❌                  | ❌             | ✅           |
| `repair.delete`            | ❌                  | ❌             | ✅           |
| `customer.view_full`       | ✅                  | ❌             | ✅           |
| `customer.view_limited`    | ✅                  | ✅             | ✅           |
| `customer.view_checked_by` | ❌                  | ❌             | ✅           |
| `manual_input.perform`     | ✅                  | ✅             | ✅           |
| `qr.scan`                  | ✅                  | ✅             | ✅           |
| `reports.view`             | ❌                  | ❌             | ✅           |
| `repair.user.view`         | ❌                  | ❌             | ✅           |
| `repair.update`            | ❌                  | ❌             | ✅           |
| `shuttle.reports`          | ❌                  | ❌             | ✅           |
| `reports.floattime.view`| ❌ | ❌ | ✅ |

## Local Permission Management

To improve performance and reduce the need for API calls, a ViewModel is employed to manage user permissions locally. This viewmodel loads the currently authenticated user's active permissions at application launch and checks against a cached list of user permissions while the application remains active. This means that if a users permissions/roles are updated while they are using the application, they may need to restart the application before the new permissions can take effect. 

**Advantages:**

- Greatly reduces the number of API calls required
- Improves performance by caching permission data