
## CloudTrail > Console Guide

### Getting Started
CloudTrail is a service provided by default when an organization is activated. If an organization has already been created, no further action is necessary.
CloudTrail can be used by selecting it from Select Service after an organization is created.

![cloudtrail_01](https://static.toastoven.net/prod_cloudtrail/EN_001.png)

### List

The following screen appears when the CloudTrail service is selected.

![cloudtrail_02](https://static.toastoven.net/prod_cloudtrail/EN_002.png)

User events are logged in the organization and users can view them.

### Searching and sorting

![cloudtrail_03](https://static.toastoven.net/prod_cloudtrail/EN_003.png)

1. Searches for users. Users can be searched by their name.
2. Searches for projects. They can be searched by name unit only.
3. Searches by source (the location where event occurred).
    - ADMIN_CONSOLE: Events occurred in the admin console
    - API: Events occurred within the system 
        - [Note] Events such as batch tasks, scheduled tasks, and alarms are logged.
    - USER_CONSOLE: Events occurred in the console of an insider member
4. Searches by service. 
    - Multiple services can be searched for.
    - [Note] Service is the unit of the TOAST cloud service.
5. Searches by event.
    - Multiple events can be searched for.
6. Searches for requests and response values.
7. Specifies the scope of a search. The filter options are 24 hours, 1 week, 2 weeks, and 3 months. Users can enter a filter value as well. 
    - [Note] Events are retained up to 3 months.
8. Specifies the list display unit. You can display 25, 50, or 100 items at once on the screen.

---

* The sort feature can only be used in the time item.

### Detailed view

![cloudtrail_04](https://static.toastoven.net/prod_cloudtrail/EN_004.png)

When a column is selected, the column is expanded and event details are displayed.

Shows requests and response results so that users can see the history of attempted requests.
