Django Admin Timezone Management
================================

This guide provides instructions on integrating and using the Django Admin Timezone Management package. The package allows administrators to select and apply a timezone for their session directly from the Django admin interface.


Overview
--------

This package enhances the Django Admin by allowing users to set their timezone preferences directly from the admin interface. Once set, the timezone is applied to the user's session, ensuring all datetime displays are consistent with the selected timezone.

Usage in Django Admin
---------------------

Once configured, the Django Admin interface will have a "Select Timezone" option in the top navigation bar.

- **Selecting a Timezone**: Administrators can click on "Select Timezone" to choose their preferred timezone from a dropdown list.

- **Timezone Display**: After setting the timezone, it will be displayed in the navigation bar, providing immediate feedback to the user.

Automatic Timezone Handling
---------------------------

The middleware handles the application of the selected timezone. When a user selects a timezone, it is stored in their session. The middleware then automatically activates this timezone for all subsequent requests during the session. If no timezone is selected, the default timezone configured in your Django settings will be used.



1. **Initial Admin Interface**: Before setting a timezone, the admin interface displays "Timezone not set."



2. **Selecting a Timezone**:The dropdown allows the user to choose from available timezones.





3. **Admin Interface After Setting Timezone**: The selected timezone is displayed, confirming that it has been applied.






4. **Model Testing**: The selected timezone will be a default time zone for django setting
