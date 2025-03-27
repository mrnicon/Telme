# API Documentation: `OrderListDynamicStatuses`

## Introduction
This document describes the API for managing dynamic statuses for orders. The API includes several steps to verify sessions, check user permissions, and retrieve order details based on various parameters.

## Endpoints

### 1. `SetAPI_JSONContentType`
- **Description**: Sets the content type for the API response to JSON.
- **Method**: No specific method mentioned, presumably an internal configuration.

### 2. `Create`
- **Description**: Creates a new log entry for API calls.
- **Parameters**:
  - `session`: Session ID.
  - `orderstatus`: Order status to filter by.
  - `workview_no`: Work view number.
  - `order_no`: Order number.
  - `startdate`: Start date for filtering orders.
  - `enddate`: End date for filtering orders.
  - `secondarysession`: Secondary session ID.
  - `object_no`: Object number.
  - `divid`: Div ID for display.
  - `search`: Search string for filtering orders.
  - `workgroup_no`: Work group number.
  - `jobtype`: Job type.
  - `subscriber_no`: Subscriber number.
- **Output**:
  - `json`: JSON response containing order details and status.

### 3. `CheckSession`
- **Description**: Checks if a session is valid.
- **Parameters**:
  - `session`: Session ID.
- **Output**:
  - `subscriber_no`: Subscriber number.
  - `user_no`: User number.

### 4. `SetWorkView`
- **Description**: Sets the work view for the session.
- **Parameters**:
  - `session`: Session ID.
  - `workview_no`: Work view number.

### 5. `CheckListOrders`
- **Description**: Checks the list of orders based on the order status.
- **Parameters**:
  - `session`: Session ID.
  - `orderstatus`: Order status to filter by.
- **Output**:
  - `status`: Status of the order list check.
  - `customer_no`: Customer number.
  - `errorcode`: Error code if the check fails.
  - `errordescription`: Error description if the check fails.

### 6. `ListGridOrders`
- **Description**: Lists orders in a grid view based on various filters.
- **Parameters**:
  - `joblist_no`: Job list number.
  - `workview_no`: Work view number.
  - `job_no`: Job number.
  - `limit`: Limit for the number of orders to retrieve.
  - `customer_no`: Customer number.
  - `profile_range`: Profile range for filtering.
  - `subscriber_no`: Subscriber number.
  - `object_no`: Object number.
  - `secondarysubscriber_no`: Secondary subscriber number.
  - `sortcolumn`: Column to sort by.
  - `user_no`: User number.
  - `statuses`: Statuses to filter by.
  - `sok_text`: Search text for filtering.
  - `sortorder`: Sort order.
  - `worklist`: Work list parameter.
  - `preservejoblist`: Preserve job list parameter.
  - `jobtypes`: Job types to filter by.
- **Output**:
  - `job_no`: Job number.
  - `ordertype`: Order type.
  - `description`: Description of the order.

### 7. `ListJobAddresses`
- **Description**: Lists job addresses for a specific job.
- **Parameters**:
  - `job_no`: Job number.
  - `type`: Type of address (e.g., "load", "unload").
- **Output**:
  - `address_no`: Address number.
  - `customeraddress_no`: Customer address number.
  - `description`: Description of the address.
  - `address`: Address details.
  - `city`: City.
  - `long`: Longitude.
  - `lat`: Latitude.
  - `contact`: Contact person.
  - `email`: Email address.
  - `phone`: Phone number.
  - `comment`: Comment.
  - `ready`: Ready status.

### 8. `ListSubJobPriceHeaders`
- **Description**: Lists price headers for sub-jobs.
- **Parameters**:
  - `job_no`: Job number.
  - `payroll`: Payroll parameter.
- **Output**:
  - `subjob_no`: Sub-job number.

### 9. `GetSubJobPrices`
- **Description**: Retrieves prices for a specific sub-job.
- **Parameters**:
  - `job_no`: Job number.
  - `payroll`: Payroll parameter.
  - `showinapp`: Show in app parameter.
- **Output**:
  - `jobprice_no`: Job price number.
  - `name`: Name of the price.
  - `quantity`: Quantity.
  - `unit`: Unit.
  - `row_no`: Row number.
  - `fields`: List of fields related to the price.

### 10. `GetJobBreak`
- **Description**: Retrieves job breaks for a specific job.
- **Parameters**:
  - `job_no`: Job number.
  - `jobbreak_no`: Job break number.
- **Output**:
  - `break_no`: Break number.
  - `starttime`: Start time for the break.
  - `endtime`: End time for the break.
  - `duration`: Duration of the break.

### 11. `ListJobFields`
- **Description**: Lists job fields for a specific job.
- **Parameters**:
  - `job_no`: Job number.
- **Output**:
  - `jobfieldtype_no`: Job field type number.
  - `name`: Field name.
  - `value`: Field value.
  - `type`: Field type.
  - `mandatory`: Indicates if the field is mandatory.
  - `id`: Field ID.
  - `defaultvalue`: Default value for the field.

## Example Code

```json
{
  "status": {
    "status": "OK",
    "OrderGrid": "true",
    "user_no": "123",
    "subscriber_no": "456",
    "startdate": "2023-10-01",
    "enddate": "2023-10-07"
  },
  "orders": [
    {
      "title": "Order 1",
      "status": "completed",
      "icon": "check-circle",
      "icon_unicode": "\\u2705",
      "color": "green",
      "mandatory_check": "true",
      "nextstatus": [
        {
          "status": "delivered",
          "name": "Delivered",
          "icon": "truck",
          "color": "blue",
          "confirmtext": "Confirm delivery",
          "type": "action",
          "action": "complete"
        }
      ],
      "nextstatuscount": "1",
      "list": [
        {
          "order_no": "ORD123",
          "date": "2023-10-01",
          "jobdate": "01 Oct 2023",
          "jobdate_small": "01 Oct",
          "jobtypename": "Delivery",
          "type": "DEL",
          "status": "completed",
          "statusicon": "check-circle",
          "ordertypeicon": "truck",
          "iconcolor": "green",
          "color": "green",
          "bgcolor": "lightgreen",
          "orderform_no": "FORM123",
          "customer": "Customer A",
          "starttime": "0800",
          "endtime": "1700",
          "reportedstarttime": "0815",
          "reportedendtime": "1715",
          "drivername": "John Doe",
          "truckregno": "ABC123",
          "truckid": "TRUCK123",
          "description": "Delivery of goods",
          "littera": "CUSTORDER123",
          "break": "1200-1300",
          "email": "john.doe@example.com",
          "id": "row1_20231001_456_ORD123",
          "workgroup_no": "WG123",
          "note": {
            "dispatch": "Ready for dispatch",
            "comment": "No comments"
          },
          "loadaddress": [
            {
              "address_no": "ADDR123",
              "customeraddress_no": "CUSTADDR123",
              "description": "Main entrance",
              "address": "123 Main St",
              "city": "Sampletown",
              "long": "12.3456",
              "lat": "67.8901",
              "contact": "Jane Smith",
              "email": "jane.smith@example.com",
              "phone": "098-765-4321",
              "comment": "Leave at door if not home",
              "ready": "true"
            }
          ],
          "unloadaddress": [
            {
              "address_no": "ADDR124",
              "customeraddress_no": "CUSTADDR124",
              "description": "Warehouse",
              "address": "456 Warehouse St",
              "city": "Sampletown",
              "long": "12.3457",
              "lat": "67.8902",
              "contact": "John Smith",
              "email": "john.smith@example.com",
              "phone": "098-765-4322",
              "comment": "Deliver to warehouse",
              "ready": "true"
            }
          ],
          "jobprice": [
            {
              "jobprice_no": "PRICE123",
              "name": "Delivery fee",
              "quantity": "1",
              "unit": "pcs",
              "row_no": "1",
              "fields": [
                {
                  "jobfieldtype_no": "FIELD123",
                  "job_no": "ORD123",
                  "row_no": "1",
                  "name": "Field Name",
                  "value": "Field Value",
                  "type": "Text",
                  "mandatory": "true",
                  "id": "field_id",
                  "defaultvalue": "Default"
                }
              ]
            }
          ],
          "truck": {
            "regno": "ABC123",
            "distance": "100 km",
            "pricedescription": "Distance price"
          },
          "breaks": [
            {
              "break_no": "BR123",
              "starttime": "1200",
              "endtime": "1300",
              "duration": "1 hour"
            }
          ],
          "fields": [
            {
              "jobfieldtype_no": "FIELD124",
              "name": "Additional Field",
              "value": "Field Value",
              "type": "Text",
              "mandatory": "false",
              "id": "additional_id",
              "defaultvalue": "Default"
            }
          ],
          "signed": "true",
          "notes": [
            {
              "row_no": "1",
              "note": "Order completed successfully",
              "datetime": "2023-10-01T08:00:00",
              "notetype": "NOTE"
            }
          ],
          "document": [
            {
              "binary_no": "BIN123",
              "name": "Invoice",
              "description": "Invoice for delivery",
              "documenttype": "PDF",
              "mimetype": "application/pdf",
              "date": "2023-10-01",
              "time": "08:00"
            }
          ],
          "paused": "false"
        }
      ]
    }
  ]
}
