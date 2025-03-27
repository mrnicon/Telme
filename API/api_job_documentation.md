
---

# API Dokumentation: `order/job`

## Inledning
Detta dokument beskriver API:et för hantering av jobb och orderinformation. API:et innehåller flera steg för att verifiera sessioner, kontrollera användarrättigheter, och hämta jobbdetaljer.

## Endpoints

### 1. `SetAPI_JSONContentType`
- **Beskrivning**: Ställer in innehållstypen för API-svaret till JSON.
- **Metod**: Ingen specifik metod nämnd, antagligen en intern konfiguration.

### 2. `Create`
- **Beskrivning**: Skapar en ny loggpost för API-anrop.
- **Parametrar**:
  - `ipaddress`: Klientens IP-adress.
  - `useragent`: Användaragentsträngen från klienten.

### 3. `AddParameter`
- **Beskrivning**: Lägger till parametrar till loggen.
- **Parametrar**:
  - `session`: Session-ID.
  - `job_no`: Jobbnummer.
  - `workview_no`: Arbetsvynummer.

### 4. `CheckSession`
- **Beskrivning**: Kontrollerar om en session är giltig.
- **Parametrar**:
  - `session`: Session-ID.
- **Utdata**:
  - `errorcode`: Felkod.
  - `errordescription`: Felbeskrivning.
  - `customer_no`: Kundnummer.
  - `user_no`: Användarnummer.
  - `owner_no`: Ägarnummer.
  - `subscriber_no`: Prenumerantnummer.

### 5. `CheckRight`
- **Beskrivning**: Kontrollerar om användaren har rättigheter för en viss åtgärd.
- **Parametrar**:
  - `user_no`: Användarnummer.
  - `right`: Rättighet att kontrollera (t.ex. `ORDER_PRICE`).
- **Utdata**:
  - `price_right`: Indikerar om användaren har rättigheten.

### 6. `ActivityJobs`
- **Beskrivning**: Hämtar jobbdetaljer baserat på kund, användare, arbetsvy, arbetsgrupp, enhet och jobbnummer.
- **Parametrar**:
  - `customer_no`: Kundnummer.
  - `user_no`: Användarnummer.
  - `workview_no`: Arbetsvynummer.
  - `workgroup_no`: Arbetsgruppnummer.
  - `unit_no`: Enhetsnummer.
  - `job_no`: Jobbnummer.
- **Utdata**:
  - `OrderForm_No`: Orderformulärnummer.
  - `Type`: Jobbtyp.
  - `Date`: Datum för jobbet.
  - `StartTime`: Starttid.
  - `EndTime`: Sluttid.
  - `ReportedStartTime`: Rapporterad starttid.
  - `ReportedEndTime`: Rapporterad sluttid.
  - `Title`: Jobbtitel.
  - `Description`: Beskrivning.
  - `Comment`: Kundkommentar.
  - `InternalInfo`: Intern information.
  - `Workgroup`: Arbetsgrupp.
  - `Workgroup_No`: Arbetsgruppnummer.
  - `UnitName`: Enhetsnamn.
  - `MainComponent`: Huvudkomponent.
  - `SubComponent`: Underkomponent.
  - `JobCostDescription`: Jobbkostnadsbeskrivning.
  - `Quantity`: Kvantitet.
  - `Unit`: Enhet.
  - `Cost`: Kostnad.
  - `Job_No`: Jobbnummer.
  - `Status`: Status.
  - `StatusName`: Statusnamn.
  - `StatusIcon`: Statusikon.
  - `StatusIconColor`: Statusikonfärg.
  - `OurReferenceName`: Vårt referensnamn.
  - `CustomerReferenceName`: Kundreferensnamn.
  - `CustomerOrderNo`: Kundorder nummer.
  - `ReferenceCode`: Referenskod.
  - `Preset_No`: Förinställningsnummer.
  - `subjobs`: Lista över underjobb.
  - `addresses`: Lista över adresser relaterade till jobbet.
  - `articles`: Lista över artiklar relaterade till jobbet.
  - `document`: Lista över dokument relaterade till jobbet.
  - `breaks`: Lista över raster för jobbet.
  - `fields`: Lista över fält relaterade till jobbet.

### 7. `GetOrderForm_No`
- **Beskrivning**: Hämtar orderformulärnummer baserat på kund och jobbtyp.
- **Parametrar**:
  - `customer_no`: Kundnummer.
  - `jobtype`: Jobbtyp.
- **Utdata**:
  - `OrderForm_No`: Orderformulärnummer.

### 8. `GetJobType`
- **Beskrivning**: Hämtar jobbtypsinformation.
- **Parametrar**:
  - `customer_no`: Kundnummer.
  - `jobtype`: Jobbtyp.
- **Utdata**:
  - `Name`: Jobbtypnamn.
  - `IconClass`: Ikonklass.
  - `Color`: Färg.
  - `BgColor`: Bakgrundsfärg.

### 9. `GetMapImageURL`
- **Beskrivning**: Hämtar URL för kartbild baserat på latitud och longitud.
- **Parametrar**:
  - `lat`: Latitud.
  - `long`: Longitud.
  - `zoom`: Zoomnivå.
- **Utdata**:
  - `url`: URL för kartbild.

### 10. `GetSubscriberProfilImage`
- **Beskrivning**: Hämtar profilbild för prenumerant.
- **Parametrar**:
  - `subscriber_no`: Prenumerantnummer.
  - `domain`: Domän.
- **Utdata**:
  - `Url`: URL för profilbild.

### 11. `GetAllSubJobPrices`
- **Beskrivning**: Hämtar alla underjobbpriser för ett specifikt jobb.
- **Parametrar**:
  - `job_no`: Jobbnummer.
  - `showinapp`: Visa i app (t.ex. `TRUE`).
- **Utdata**:
  - `Job_No`: Jobbnummer.
  - `Price_No`: Prisnummer.
  - `Description`: Beskrivning.
  - `Unit`: Enhet.
  - `UniqueId`: Unikt ID.
  - `JobCostRow_No`: Jobbkostnadsradnummer.
  - `Price`: Pris.
  - `Quantity`: Kvantitet.
  - `DiscountRate`: Rabattsats.
  - `DiscountType`: Rabatttyp.
  - `Sum`: Summa.
  - `JobPrice_No`: Jobbprisnummer.

### 12. `GetArticleImageUrl`
- **Beskrivning**: Hämtar URL för artikelbild.
- **Parametrar**:
  - `price_no`: Prisnummer.
  - `domain`: Domän.
- **Utdata**:
  - `url`: URL för artikelbild.

### 13. `GetJobBreak`
- **Beskrivning**: Hämtar jobbraster för ett specifikt jobb.
- **Parametrar**:
  - `job_no`: Jobbnummer.
  - `jobbreak_no`: Jobbrastnummer.
- **Utdata**:
  - `JobBreak_No`: Jobbrastnummer.
  - `StartTime`: Starttid.
  - `EndTime`: Sluttid.
  - `Duration`: Varaktighet.

## Exempelkod

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

## Fältbeskrivningar

### Parametrar

| **Fält**          | **Beskrivning**                                                                 |
|-------------------|---------------------------------------------------------------------------------|
| `ipaddress`       | Klientens IP-adress.                                                            |
| `useragent`       | Användaragentsträngen från klienten.                                            |
| `session`         | Session-ID.                                                                     |
| `job_no`          | Jobbnummer.                                                                     |
| `workview_no`     | Arbetsvynummer.                                                                 |
| `customer_no`     | Kundnummer.                                                                     |
| `user_no`         | Användarnummer.                                                                 |
| `right`           | Rättighet att kontrollera (t.ex. `ORDER_PRICE`).                                |
| `workgroup_no`    | Arbetsgruppnummer.                                                              |
| `unit_no`         | Enhetsnummer.                                                                   |
| `lat`             | Latitud för kartbild.                                                           |
| `long`            | Longitud för kartbild.                                                          |
| `zoom`            | Zoomnivå för kartbild.                                                          |
| `subscriber_no`   | Prenumerantnummer.                                                              |
| `domain`          | Domän för att hämta bilder.                                                     |
| `jobbreak_no`     | Jobbrastnummer.                                                                 |
| `showinapp`       | Visa i app (t.ex. `TRUE`).                                                      |

### Resultatfält

| **Fält**                  | **Beskrivning**                                                                 |
|---------------------------|---------------------------------------------------------------------------------|
| `errorcode`               | Felkod som indikerar om ett fel har inträffat.                                 |
| `errordescription`        | Beskrivning av felet.                                                           |
| `price_right`             | Indikerar om användaren har rättigheter för prisinformation.                   |
| `OrderForm_No`            | Orderformulärnummer.                                                            |
| `Type`                    | Typ av jobb.                                                                    |
| `Date`                    | Datum för jobbet.                                                               |
| `StartTime`               | Starttid för jobbet.                                                            |
| `EndTime`                 | Sluttid för jobbet.                                                             |
| `ReportedStartTime`       | Rapporterad starttid.                                                           |
| `ReportedEndTime`         | Rapporterad sluttid.                                                            |
| `Title`                   | Jobbtitel.                                                                      |
| `Description`             | Beskrivning av jobbet.                                                          |
| `Comment`                 | Kundkommentar.                                                                  |
| `InternalInfo`            | Intern information om jobbet.                                                  |
| `Workgroup`               | Arbetsgrupp.                                                                    |
| `Workgroup_No`            | Arbetsgruppnummer.                                                              |
| `UnitName`                | Namn på enheten.                                                                |
| `MainComponent`           | Huvudkomponent.                                                                 |
| `SubComponent`            | Underkomponent.                                                                 |
| `JobCostDescription`      | Beskrivning av jobbkostnad.                                                     |
| `Quantity`                | Kvantitet.                                                                      |
| `Unit`                    | Enhet.                                                                          |
| `Cost`                    | Kostnad.                                                                        |
| `Job_No`                  | Jobbnummer.                                                                     |
| `Status`                  | Status för jobbet.                                                              |
| `StatusName`              | Namn på status.                                                                 |
| `StatusIcon`              | Ikon för status.                                                                |
| `StatusIconColor`         | Färg för statusikon.                                                            |
| `OurReferenceName`        | Vårt referensnamn.                                                              |
| `CustomerReferenceName`   | Kundreferensnamn.                                                               |
| `CustomerOrderNo`         | Kundorder nummer.                                                               |
| `ReferenceCode`           | Referenskod.                                                                    |
| `Preset_No`               | Förinställningsnummer.                                                          |
| `subjobs`                 | Lista över underjobb.                                                           |
| `addresses`               | Lista över adresser relaterade till jobbet.                                     |
| `articles`                | Lista över artiklar relaterade till jobbet.                                     |
| `document`                | Lista över dokument relaterade till jobbet.                                     |
| `breaks`                  | Lista över raster för jobbet.                                                   |
| `fields`                  | Lista över fält relaterade till jobbet.                                         |

### Underobjekt

#### `subjobs`

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobtype`             | Typ av underjobb.                                                               |
| `jobtypename`         | Namn på underjobb.                                                              |
| `iconclass`           | Ikonklass för underjobb.                                                        |
| `color`               | Färg för underjobb.                                                             |
| `bgcolor`             | Bakgrundsfärg för underjobb.                                                    |
| `subscribers`         | Lista över prenumeranter för underjobb.                                         |

#### `subscribers`

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `job_no`              | Jobbnummer för underjobb.                                                       |
| `type`                | Typ av underjobb.                                                               |
| `typename`            | Namn på underjobb.                                                              |
| `subscriber_no`       | Prenumerantnummer.                                                              |
| `fullname`            | Fullständigt namn på prenumerant.                                               |
| `lastname`            | Efternamn.                                                                      |
| `firstname`           | Förnamn.                                                                        |
| `title`               | Titel.                                                                          |
| `company`             | Företag.                                                                        |
| `email`               | E-postadress.                                                                   |
| `mobile`              | Mobiltelefonnummer.                                                             |
| `initials`            | Initialer.                                                                      |
| `personid`            | Person-ID.                                                                      |
| `info`                | Information om prenumerant.                                                     |
| `imageurl`            | URL för profilbild.                                                             |

#### `addresses`

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobaddress_no`       | Jobbadressnummer.                                                               |
| `row_no`              | Radnummer.                                                                      |
| `organisationaddress_no` | Organisationsadressnummer.                                                     |
| `type`                | Typ av adress.                                                                  |
| `address`             | Adress.                                                                         |
| `address2`            | Adressrad 2.                                                                   |
| `description`         | Beskrivning av adress.                                                          |
| `zip`                 | Postnummer.                                                                     |
| `city`                | Stad.                                                                           |
| `land`                | Land.                                                                           |
| `state`               | Delstat.                                                                        |
| `directions`          | Vägbeskrivning.                                                                 |
| `contact`             | Kontaktperson.                                                                  |
| `email`               | E-postadress.                                                                   |
| `phone`               | Telefonnummer.                                                                  |
| `longitude`           | Longitud.                                                                       |
| `latitude`            | Latitud.                                                                        |
| `comment`             | Kommentar.                                                                      |
| `visittime`           | Besökstid.                                                                      |
| `ready`               | Klarstatus.                                                                     |
| `imageurl`            | URL för kartbild.                                                               |

#### `articles`

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `price_no`            | Prisnummer.                                                                     |
| `articleid`           | Artikel-ID.                                                                     |
| `name`                | Namn på artikel.                                                                |
| `description`         | Beskrivning av artikel.                                                         |
| `unit`                | Enhet.                                                                          |
| `row`                 | Rad-ID.                                                                         |
| `row_no`              | Radnummer.                                                                      |
| `cost`                | Kostnad.                                                                        |
| `quantity`            | Kvantitet.                                                                      |
| `discount`            | Rabattsats.                                                                     |
| `discounttype`        | Rabatttyp.                                                                      |
| `sum`                 | Summa.                                                                          |
| `jobprice_no`         | Jobbprisnummer.                                                                 |
| `job_no`              | Jobbnummer.                                                                     |
| `imageurl`            | URL för artikelbild.                                                            |
| `fields`              | Lista över fält relaterade till artikel.                                        |

#### `fields` (inom `articles`)

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobfieldtype_no`     | Fälttypnummer.                                                                  |
| `name`                | Namn på fält.                                                                   |
| `job_no`              | Jobbnummer.                                                                     |
| `row_no`              | Radnummer.                                                                      |
| `value`               | Värde för fältet.                                                               |
| `description`         | Beskrivning av fältet.                                                          |
| `icon`                | Ikon för fältet.                                                                |
| `type`                | Typ av fält.                                                                    |
| `mandatory`           | Indikerar om fältet är obligatoriskt.                                          |
| `id`                  | Fält-ID.                                                                        |
| `defaultvalue`        | Standardvärde för fältet.                                                       |
| `apptab`              | Flik för fältet i applikationen.                                               |

#### `document`

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `binary_no`           | Binärnummer för dokument.                                                       |
| `name`                | Namn på dokument.                                                               |
| `description`         | Beskrivning av dokument.                                                        |
| `documenttype`        | Typ av dokument.                                                                |
| `mimetype`            | MIME-typ för dokument.                                                          |
| `date`                | Datum för dokument.                                                             |
| `time`                | Tid för dokument.                                                               |
| `filename`            | Filnamn för dokument.                                                           |
| `url`                 | URL för att ladda ner dokument.                                                |

#### `breaks`

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `break_no`            | Rastnummer.                                                                     |
| `starttime`           | Starttid för rast.                                                              |
| `endtime`             | Sluttid för rast.                                                               |
| `duration`            | Varaktighet för rast.                                                           |

#### `fields` (i huvudobjektet)

| **Fält**              | **Beskrivning**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| `jobfieldtype_no`     | Fälttypnummer.                                                                  |
| `name`                | Namn på fält.                                                                   |
| `job_no`              | Jobbnummer.                                                                     |
| `row_no`              | Radnummer.                                                                      |
| `value`               | Värde för fältet.                                                               |
| `description`         | Beskrivning av fältet.                                                          |
| `icon`                | Ikon för fältet.                                                                |
| `type`                | Typ av fält.                                                                    |
| `mandatory`           | Indikerar om fältet är obligatoriskt.                                          |
| `id`                  | Fält-ID.                                                                        |
| `defaultvalue`        | Standardvärde för fältet.                                                       |
| `apptab`              | Flik för fältet i applikationen.                                               |

---
