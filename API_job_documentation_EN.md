
# API Documentation: `order/job`

## Introduction
This document describes the API for managing jobs and order information. The API includes several steps to verify sessions, check user permissions, and retrieve job details.

## Endpoints

### 1. `SetAPI_JSONContentType`
- **Description**: Sets the content type for the API response to JSON.
- **Method**: No specific method mentioned, presumably an internal configuration.

### 2. `Create`
- **Description**: Creates a new log entry for API calls.
- **Parameters**:
  - `ipaddress`: Client's IP address.
  - `useragent`: User-agent string from the client.

### 3. `AddParameter`
- **Description**: Adds parameters to the log.
- **Parameters**:
  - `session`: Session ID.
  - `job_no`: Job number.
  - `workview_no`: Work view number.

### 4. `CheckSession`
- **Description**: Checks if a session is valid.
- **Parameters**:
  - `session`: Session ID.
- **Output**:
  - `errorcode`: Error code.
  - `errordescription`: Error description.
  - `customer_no`: Customer number.
  - `user_no`: User number.
  - `owner_no`: Owner number.
  - `subscriber_no`: Subscriber number.

### 5. `CheckRight`
- **Description**: Checks if the user has rights for a specific action.
- **Parameters**:
  - `user_no`: User number.
  - `right`: Right to check (e.g., `ORDER_PRICE`).
- **Output**:
  - `price_right`: Indicates if the user has the right.

### 6. `ActivityJobs`
- **Description**: Retrieves job details based on customer, user, work view, work group, unit, and job number.
- **Parameters**:
  - `customer_no`: Customer number.
  - `user_no`: User number.
  - `workview_no`: Work view number.
  - `workgroup_no`: Work group number.
  - `unit_no`: Unit number.
  - `job_no`: Job number.
- **Output**:
  - `OrderForm_No`: Order form number.
  - `Type`: Job type.
  - `Date`: Date for the job.
  - `StartTime`: Start time.
  - `EndTime`: End time.
  - `ReportedStartTime`: Reported start time.
  - `ReportedEndTime`: Reported end time.
  - `Title`: Job title.
  - `Description`: Description.
  - `Comment`: Customer comment.
  - `InternalInfo`: Internal information.
  - `Workgroup`: Work group.
  - `Workgroup_No`: Work group number.
  - `UnitName`: Unit name.
  - `MainComponent`: Main component.
  - `SubComponent`: Sub-component.
  - `JobCostDescription`: Job cost description.
  - `Quantity`: Quantity.
  - `Unit`: Unit.
  - `Cost`: Cost.
  - `Job_No`: Job number.
  - `Status`: Status.
  - `StatusName`: Status name.
  - `StatusIcon`: Status icon.
  - `StatusIconColor`: Status icon color.
  - `OurReferenceName`: Our reference name.
  - `CustomerReferenceName`: Customer reference name.
  - `CustomerOrderNo`: Customer order number.
  - `ReferenceCode`: Reference code.
  - `Preset_No`: Preset number.
  - `subjobs`: List of sub-jobs.
  - `addresses`: List of addresses related to the job.
  - `articles`: List of articles related to the job.
  - `document`: List of documents related to the job.
  - `breaks`: List of breaks for the job.
  - `fields`: List of fields related to the job.

### 7. `GetOrderForm_No`
- **Description**: Retrieves the order form number based on customer and job type.
- **Parameters**:
  - `customer_no`: Customer number.
  - `jobtype`: Job type.
- **Output**:
  - `OrderForm_No`: Order form number.

### 8. `GetJobType`
- **Description**: Retrieves job type information.
- **Parameters**:
  - `customer_no`: Customer number.
  - `jobtype`: Job type.
- **Output**:
  - `Name`: Job type name.
  - `IconClass`: Icon class.
  - `Color`: Color.
  - `BgColor`: Background color.

### 9. `GetMapImageURL`
- **Description**: Retrieves the URL for a map image based on latitude and longitude.
- **Parameters**:
  - `lat`: Latitude.
  - `long`: Longitude.
  - `zoom`: Zoom level.
- **Output**:
  - `url`: URL for the map image.

### 10. `GetSubscriberProfilImage`
- **Description**: Retrieves the profile image for a subscriber.
- **Parameters**:
  - `subscriber_no`: Subscriber number.
  - `domain`: Domain.
- **Output**:
  - `Url`: URL for the profile image.

### 11. `GetAllSubJobPrices`
- **Description**: Retrieves all sub-job prices for a specific job.
- **Parameters**:
  - `job_no`: Job number.
  - `showinapp`: Show in app (e.g., `TRUE`).
- **Output**:
  - `Job_No`: Job number.
  - `Price_No`: Price number.
  - `Description`: Description.
  - `Unit`: Unit.
  - `UniqueId`: Unique ID.
  - `JobCostRow_No`: Job cost row number.
  - `Price`: Price.
  - `Quantity`: Quantity.
  - `DiscountRate`: Discount rate.
  - `DiscountType`: Discount type.
  - `Sum`: Sum.
  - `JobPrice_No`: Job price number.

### 12. `GetArticleImageUrl`
- **Description**: Retrieves the URL for an article image.
- **Parameters**:
  - `price_no`: Price number.
  - `domain`: Domain.
- **Output**:
  - `url`: URL for the article image.

### 13. `GetJobBreak`
- **Description**: Retrieves job breaks for a specific job.
- **Parameters**:
  - `job_no`: Job number.
  - `jobbreak_no`: Job break number.
- **Output**:
  - `JobBreak_No`: Job break number.
  - `StartTime`: Start time.
  - `EndTime`: End time.
  - `Duration`: Duration.

## Example Code

```json
{
  "job": {
    "year": "2023",
    "date": "2023-10-01",
    "starttime": "08:00",
    "endtime": "17:00",
    "reportedstarttime": "08:15",
    "reportedendtime": "17:15",
    "title": "Installation",
    "type": "Service",
    "description": "Install new equipment.",
    "customercomment": "Please arrive early.",
    "internalinfo": "Requires special tools.",
    "workgroup": "Installation Team",
    "workgroup_no": "101",
    "unitname": "Unit A",
    "maincomponent": "Main Board",
    "subcomponent": "Sub Board",
    "article": "Installation Kit",
    "quantity": "2",
    "unit": "pcs",
    "cost": "150.00",
    "job_no": "12345",
    "status": "Completed",
    "statusname": "Completed",
    "statusicon": "check-circle",
    "statusiconcolor": "green",
    "ourreferencename": "Project X",
    "customerreferencename": "Client Y",
    "customerorderno": "CUST123",
    "referencecode": "REF456",
    "preset_no": "789",
    "subjobs": [
      {
        "jobtype": "SubTask",
        "jobtypename": "Sub Task",
        "iconclass": "task-icon",
        "color": "blue",
        "bgcolor": "lightblue",
        "subscribers": [
          {
            "job_no": "12345-1",
            "type": "SubTask",
            "typename": "Sub Task",
            "subscriber_no": "54321",
            "fullname": "John Doe",
            "lastname": "Doe",
            "firstname": "John",
            "title": "Technician",
            "company": "Tech Corp",
            "email": "john.doe@techcorp.com",
            "mobile": "123-456-7890",
            "initials": "JD",
            "personid": "P123",
            "info": "Experienced technician",
            "imageurl": "https://example.com/profile/john.jpg"
          }
        ]
      }
    ],
    "addresses": [
      {
        "jobaddress_no": "67890",
        "row_no": "1",
        "organisationaddress_no": "ORG123",
        "type": "Delivery",
        "address": "123 Main St",
        "address2": "Apt 4B",
        "description": "Main entrance",
        "zip": "12345",
        "city": "Sampletown",
        "land": "Country",
        "state": "State",
        "directions": "Follow main road",
        "contact": "Jane Smith",
        "email": "jane.smith@example.com",
        "phone": "098-765-4321",
        "longitude": "12.3456",
        "latitude": "67.8901",
        "comment": "Leave at door if not home",
        "visittime": "10:00",
        "ready": "Yes",
        "imageurl": "https://example.com/map/123MainSt.jpg"
      }
    ],
    "articles": [
      {
        "price_no": "P987",
        "articleid": "ART123",
        "name": "Installation Kit",
        "description": "Kit for installation",
        "unit": "pcs",
        "row": "R123",
        "row_no": "1",
        "cost": "150.00",
        "quantity": "2",
        "discount": "0",
        "discounttype": "None",
        "sum": "300.00",
        "jobprice_no": "JP654",
        "job_no": "12345",
        "imageurl": "https://example.com/articles/installationkit.jpg",
        "fields": [
          {
            "jobfieldtype_no": "F123",
            "name": "Field Name",
            "job_no": "12345",
            "row_no": "1",
            "value": "Field Value",
            "description": "Field Description",
            "icon": "field-icon",
            "type": "Text",
            "mandatory": "Yes",
            "id": "field_id",
            "defaultvalue": "Default",
            "apptab": "Main"
          }
        ]
      }
    ],
    "document": [
      {
        "binary_no": "B123",
        "name": "Document Name",
        "description": "Document Description",
        "documenttype": "PDF",
        "mimetype": "application/pdf",
        "date": "2023-10-01",
        "time": "12:00",
        "filename": "document.pdf",
        "url": "https://example.com/download/document.pdf"
      }
    ],
    "breaks": [
      {
        "break_no": "BR456",
        "starttime": "12:00",
        "endtime": "13:00",
        "duration": "1 hour"
      }
    ],
    "fields": [
      {
        "jobfieldtype_no": "F789",
        "name": "Additional Field",
        "job_no": "12345",
        "row_no": "",
        "value": "Field Value",
        "description": "Additional Field Description",
        "icon": "additional-icon",
        "type": "Text",
        "mandatory": "No",
        "id": "additional_id",
        "defaultvalue": "Default",
        "apptab": "Extra"
      }
    ]
  }
}
```

## Field Descriptions

### Parameters

| **Field**          | **Description**                                                                 |
|-------------------|---------------------------------------------------------------------------------|
| `ipaddress`       | Client's IP address.                                                            |
| `useragent`       | User-agent string from the client.                                            |
| `session`         | Session ID.                                                                     |
| `job_no`          | Job number.                                                                     |
| `workview_no`     | Work view number.                                                                 |
| `customer_no`     | Customer number.                                                                 |
| `user_no`         | User number.                                                                 |
| `right`           | Right to check (e.g., `ORDER_PRICE`).                                          |
| `workgroup_no`    | Work group number.                                                              |
| `unit_no`         | Unit number.                                                                   |
| `lat`             | Latitude for the map image.                                                     |
| `long`            | Longitude for the map image.                                                    |
| `zoom`            | Zoom level for the map image.                                                  |
| `subscriber_no`   | Subscriber number.                                                              |
| `domain`          | Domain for retrieving images.                                                 |
| `jobbreak_no`     | Job break number.                                                               |
| `showinapp`       | Show in app (e.g., `TRUE`).                                                      |

### Output Fields

| **Field**                  | **Description**                                                                 |
|---------------------------|---------------------------------------------------------------------------------|
| `errorcode`               | Error code indicating if an error occurred.                                   |
| `errordescription`        | Description of the error.                                                       |
| `price_right`             | Indicates if the user has the right for price information.                     |
| `OrderForm_No`            | Order form number.                                                              |
| `Type`                    | Job type.                                                                       |
| `Date`                    | Date for the job.                                                              |
| `StartTime`               | Start time for the job.                                                        |
| `EndTime`                 | End time for the job.                                                           |
| `ReportedStartTime`       | Reported start time.                                                            |
| `ReportedEndTime`         | Reported end time.                                                             |
| `Title`                   | Job title.                                                                      |
| `Description`             | Description of the job.                                                          |
| `Comment`                 | Customer comment.                                                               |
| `InternalInfo`            | Internal information about the job.                                             |
| `Workgroup`               | Work group.                                                                     |
| `Workgroup_No`            | Work group number.                                                             |
| `UnitName`                | Unit name.                                                                      |
| `MainComponent`           | Main component.                                                                |
| `SubComponent`            | Sub-component.                                                                  |
| `JobCostDescription`      | Job cost description.                                                         |
| `Quantity`                | Quantity.                                                                       |
| `Unit`                    | Unit.                                                                           |
| `Cost`                    | Cost.                                                                           |
| `Job_No`                  | Job number.                                                                     |
| `Status`                  | Status of the job.                                                              |
| `StatusName`              | Status name.                                                                    |
| `StatusIcon`              | Status icon.                                                                    |
| `StatusIconColor`         | Status icon color.                                                             |
| `OurReferenceName`        | Our reference name.                                                             |
| `CustomerReferenceName`   | Customer reference name.                                                        |
| `CustomerOrderNo`         | Customer order number.                                                          |
| `ReferenceCode`           | Reference code.                                                                |
| `Preset_No`               | Preset number.                                                                 |
| `subjobs`                 | List of sub-jobs.                                                               |
| `addresses`               | List of addresses related to the job.                                           |
| `articles`                | List of articles related to the job.                                            |
| `document`                | List of documents related to the job.                                           |
| `breaks`                  | List of breaks for the job.                                                    |
| `fields`                  | List of fields related to the job.                                             |

### Sub-objects

#### `subjobs`

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobtype`             | Sub-job type.                                                                  |
| `jobtypename`         | Sub-job type name.                                                               |
| `iconclass`           | Icon class for the sub-job.                                                    |
| `color`               | Color for the sub-job.                                                          |
| `bgcolor`             | Background color for the sub-job.                                               |
| `subscribers`         | List of subscribers for the sub-job.                                           |

#### `subscribers`

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `job_no`              | Job number for the sub-job.                                                    |
| `type`                | Sub-job type.                                                                   |
| `typename`            | Sub-job type name.                                                              |
| `subscriber_no`       | Subscriber number.                                                              |
| `fullname`            | Full name of the subscriber.                                                   |
| `lastname`            | Last name.                                                                      |
| `firstname`           | First name.                                                                     |
| `title`               | Title.                                                                          |
| `company`             | Company.                                                                        |
| `email`               | Email address.                                                                  |
| `mobile`              | Mobile phone number.                                                             |
| `initials`            | Initials.                                                                      |
| `personid`            | Person ID.                                                                      |
| `info`                | Information about the subscriber.                                               |
| `imageurl`            | URL for the profile image.                                                      |

#### `addresses`

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobaddress_no`       | Job address number.                                                            |
| `row_no`              | Row number.                                                                     |
| `organisationaddress_no` | Organization address number.                                                   |
| `type`                | Address type.                                                                   |
| `address`             | Address.                                                                        |
| `address2`            | Address line 2.                                                                |
| `description`         | Description of the address.                                                     |
| `zip`                 | Zip code.                                                                       |
| `city`                | City.                                                                           |
| `land`                | Country.                                                                        |
| `state`               | State.                                                                          |
| `directions`          | Directions.                                                                     |
| `contact`             | Contact person.                                                                 |
| `email`               | Email address.                                                                  |
| `phone`               | Phone number.                                                                   |
| `longitude`           | Longitude.                                                                      |
| `latitude`            | Latitude.                                                                       |
| `comment`             | Comment.                                                                        |
| `visittime`           | Visit time.                                                                     |
| `ready`               | Ready status.                                                                  |
| `imageurl`            | URL for the map image.                                                          |

#### `articles`

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `price_no`            | Price number.                                                                  |
| `articleid`           | Article ID.                                                                     |
| `name`                | Article name.                                                                   |
| `description`         | Description of the article.                                                     |
| `unit`                | Unit.                                                                          |
| `row`                 | Row ID.                                                                         |
| `row_no`              | Row number.                                                                     |
| `cost`                | Cost.                                                                           |
| `quantity`            | Quantity.                                                                        |
| `discount`            | Discount rate.                                                                  |
| `discounttype`        | Discount type.                                                                   |
| `sum`                 | Sum.                                                                           |
| `jobprice_no`         | Job price number.                                                               |
| `job_no`              | Job number.                                                                     |
| `imageurl`            | URL for the article image.                                                      |
| `fields`              | List of fields related to the article.                                          |

#### `fields` (within `articles`)

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobfieldtype_no`     | Field type number.                                                              |
| `name`                | Field name.                                                                     |
| `job_no`              | Job number.                                                                     |
| `row_no`              | Row number.                                                                     |
| `value`               | Value for the field.                                                             |
| `description`         | Description of the field.                                                        |
| `icon`                | Icon for the field.                                                             |
| `type`                | Field type.                                                                     |
| `mandatory`           | Indicates if the field is mandatory.                                           |
| `id`                  | Field ID.                                                                       |
| `defaultvalue`        | Default value for the field.                                                    |
| `apptab`              | Tab for the field in the application.                                           |

#### `document`

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `binary_no`           | Binary number for the document.                                                |
| `name`                | Document name.                                                                  |
| `description`         | Description of the document.                                                      |
| `documenttype`        | Document type.                                                                  |
| `mimetype`            | MIME type for the document.                                                    |
| `date`                | Date for the document.                                                          |
| `time`                | Time for the document.                                                           |
| `filename`            | File name for the document.                                                     |
| `url`                 | URL to download the document.                                                  |

#### `breaks`

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `break_no`            | Break number.                                                                   |
| `starttime`           | Start time for the break.                                                       |
| `endtime`             | End time for the break.                                                         |
| `duration`            | Duration of the break.                                                          |

#### `fields` (in the main object)

| **Field**              | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobfieldtype_no`     | Field type number.                                                              |
| `name`                | Field name.                                                                     |
| `job_no`              | Job number.                                                                     |
| `row_no`              | Row number.                                                                     |
| `value`               | Value for the field.                                                             |
| `description`         | Description of the field.                                                        |
| `icon`                | Icon for the field.                                                             |
| `type`                | Field type.                                                                     |
| `mandatory`           | Indicates if the field is mandatory.                                           |
| `id`                  | Field ID.                                                                       |
| `defaultvalue`        | Default value for the field.                                                    |
| `apptab`              | Tab for the field in the application.                                           |

