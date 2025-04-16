# 🧭 InnovaTrip Ontology — README

## 🌍 Domain: Tourism

The chosen domain for this project is **tourism**, a vital field in economic, social, and cultural development worldwide. The **InnovaTrip Ontology** models key tourism-related concepts such as **tourists**, **guides**, **service providers**, **places**, **bookings**, **transportation**, and **media**, enabling semantic structuring and querying of information in tourism-related applications.

---

## 📐 Model Used

This ontology was built using **RDF/OWL** standards via **Protégé**. It follows a class-based modeling approach where concepts are represented as **classes**, connected via **object properties**, and enriched with **data properties**.

---

## 🧭 Namespaces Used

| Prefix     | Namespace URL |
|------------|----------------|
| `rdf`      | http://www.w3.org/1999/02/22-rdf-syntax-ns# |
| `rdfs`     | http://www.w3.org/2000/01/rdf-schema# |
| `owl`      | http://www.w3.org/2002/07/owl# |
| `xsd`      | http://www.w3.org/2001/XMLSchema# |
| `foaf`     | http://xmlns.com/foaf/0.1/ |
| `dc`       | http://purl.org/dc/elements/1.1/ |
| `innova`   | http://www.semanticweb.org/yassineeya/InnovaTrip# |

### ✅ Justification:
- `foaf`: to describe people (e.g., names, personal info).
- `dc`: to provide metadata like creators, creation date, and description.
- `innova`: the custom namespace for our ontology elements.
- `rdf`, `rdfs`, `owl`: standard for OWL and RDF definitions.

> ℹ️ Metadata using `dc:` includes:
```xml
<dc:creator>Eya SGHAIER</dc:creator>
<dc:creator>Mohamed Yassine REKIK</dc:creator>
<dc:title>InnovaTrip Ontology</dc:title>
<dc:date>2025-04-01</dc:date>
<dc:description>
An ontology modeling the tourism domain including tourists, guides, service providers, bookings, etc.
</dc:description>
```
---

## 🧩 Model Description

### 🔷 Main Classes

- Person
    - Tourist
    - Guide
    - ServiceProvider

- Place
    - Attraction
        - Beach
        - Monument
        - Museum
        - Park
    - City
    - Country

- Activity
    - Cultural
        - HeritageTour
        - MuseumVisit
    - Outdoor
        - Diving
        - Hiking

- Accommodation
    - GuestHouse
    - Hostel
    - Hotel

- Booking
    - AccommodationBooking
    - ActivityBooking

- Review
    - AttractionReview
    - HotelReview

- Media
    - Photo
    - Video

- Transport
    - Private
        - Taxi
        - CarRental
    - Public
        - Bus
        - Train

---

### 🧬 Data Properties

| Property            | Domain(s)                         | Range           | Description                                 |
|---------------------|-----------------------------------|-----------------|---------------------------------------------|
| ` age`              | Tourist ,Guide, ServiceProvider   | xsd:integer     | Age of the tourist                          |
| ` areaSize`         | Park                              | xsd:float       | Size of the park                            |
| ` nationality`      | Tourist                           | xsd:string      | Nationality of the tourist                  |
| ` experienceYears`  | Guide                             | xsd:integer     | Number of years of guiding experience       |
| ` languagesSpoken`  | Guide                             | xsd:string      | Languages spoken by the guide               |
| ` rating`           | ServiceProvider, Review           | xsd:float       | Assigned rating for the provider            |
| ` companyName`      | ServiceProvider                   | xsd:string      | Name of the service provider's company      |
| ` difficultyLevel`  | Hiking                            | xsd:string      | Level of difficulty of the hiking trail     |
| ` depthLevel`       | Diving                            | xsd:int         | Depth level of the diving activity          |
| ` museumName`       | MuseumVisit                       | xsd:string      | Name of the visited museum                  |
| ` tourType`         | HeritageTour                      | xsd:string      | Type of heritage tour                       |
| ` price`            | Trans,Booking, Attr,Accommodation | xsd:float       | Price of the service or booking             |
| ` busRoute`         | Bus                               | xsd:string      | Bus route name or number                    |
| ` trainRoute`       | Train                             | xsd:string      | Train route name or number                  |
| ` availableSeats`   | Taxi                              | xsd:int         | Number of available seats in the taxi       |
| ` carModel`         | CarRental                         | xsd:string      | Model of the rented car                     |
| ` bookingDate`      | Booking                           | xsd:date        | Date the booking was made                   |
| ` reviewText`       | Review                            | xsd:string      | Content of the review                       |
| ` reviewDate`       | Review                            | xsd:date        | Date the review was written                 |
| ` mediaURL`         | Media                             | xsd:string      | Media link (URL)                            |
| ` imageResolution`  | Photo                             | xsd:string      | Resolution of the image                     |
| ` videoDuration`    | Video                             | xsd:int         | Duration of the video in seconds            |
| ` capacity`         |Accommodation                      | xsd:int         | Capacity of an accommodation                |
| ` duration`         |Activity                           | xsd:int         | Duration of an activity                     |
| ` exhibitionType`   |Musuem                             | xsd:string      | Type of an exhibition                       |
| ` facilities`       |Beach                              | xsd:string      | Facilities of the Beach                     |
| ` openingHours`     |Attraction,Pa,Bea,Mus,Monum        | xsd:string      | Hours of Openings                           |
| ` name`             |Place                              | xsd:string      | Name of a Place                             |
| ` location`         |Accommodation                      | xsd:string      | Location of an accommodation                |
| ` historicalSignif` |Place                              | xsd:string      | The historical significance of a Monument   |

---

### 🔗 Object Properties

| Property                   | Domain          | Range         | Description                                           |
|---------------------------|------------------|---------------|-------------------------------------------------------|
| `booksAccommodation`      | Tourist          | Accommodation | A tourist books an accommodation                      |
| `guidesActivity`          | Guide            | Activity      | A guide is responsible for an activity                |
| `hasAttraction`           | Place            | Attraction    | A place includes or features an attraction            |
| `madeBy`                  | Booking          | Tourist       | A booking is made by a tourist                        |
| `mediaOf`                 | Media            | Attraction    | Media is associated with an attraction                |
| `participatesIn`          | Tourist          | Activity      | A tourist participates in an activity                 |
| `reserves`                | Booking          | Accommodation | A booking reserves a specific accommodation           |
| `reviewsAccommodation`    | Review           | Accommodation | A review evaluates an accommodation                   |
| `reviewsAttraction`       | Review           | Attraction    | A review evaluates an attraction                      |
| `takesPlaceAt`            | Activity         | Place         | An activity takes place at a specific place           |
| `usesTransport`           | Tourist          | Transport     | A tourist uses a transport service                    |
| `writesReview`            | Tourist          | Review        | A tourist writes a review                             |

---

## 📑 Description of SPARQL Queries and Their Meaning

This section explains each SPARQL query used in the `InnovaTrip` ontology project, what it is designed to retrieve, and what kind of results it should produce.

---

### 🟢 Simple SPARQL Queries

#### 1. Get all tourists' names
- **Query Purpose**: Retrieves all individuals of type `Tourist` and their names using the `foaf:name` property.
- **Expected Results**: A list of tourists with their associated names.

#### 2. Get all bookings and their prices
- **Query Purpose**: Retrieves every `Booking` and its corresponding `price`.
- **Expected Results**: A table with bookings and their associated price values.

#### 3. Get all reviews with their text
- **Query Purpose**: Fetches all `Review` instances and displays the written content (`reviewText`).
- **Expected Results**: A list of reviews and the text written by tourists.

#### 4. Get all media and their URLs
- **Query Purpose**: Lists all media elements (images, videos, etc.) and their associated URLs.
- **Expected Results**: A list of media entries with their respective media URLs.

#### 5. Get all transport services and their prices
- **Query Purpose**: Filters transport services like Bus, Train, Taxi, and CarRental and shows their prices.
- **Expected Results**: A table with transport types and their prices.

#### 6. Get all bookings and their dates
- **Query Purpose**: Displays each booking and the corresponding date of the reservation.
- **Expected Results**: A list of bookings along with their booking dates.

#### 7. Get all service providers with their ratings
- **Query Purpose**: Lists all individuals or entities that are `ServiceProvider`s with their given `rating`.
- **Expected Results**: A table of service providers and how they are rated.

#### 8. Find tourists who are younger than 30
- **Query Purpose**: Filters tourists whose `age` is less than 30.
- **Expected Results**: A list of younger tourists with their age displayed.

---

### 🔷 More Complex SPARQL Queries

#### 9. Find service providers with a rating greater than 4
- **Query Purpose**: Selects highly-rated service providers by applying a filter on `rating`.
- **Expected Results**: Providers with a rating higher than 4, sorted from highest to lowest.

#### 10. Get the name and nationality of tourists younger than 30 and from French nationality
- **Query Purpose**: Retrieves `foaf:name` and `nationality` for tourists who are French and under 30 years old.
- **Expected Results**: A refined list showing French tourists below 30, with their names and nationality.

#### 11. List all photos with their resolution and the place they describe
- **Query Purpose**: Displays all `Photo` instances with their `imageResolution` and the `Place` they are linked to via `mediaOf`.
- **Expected Results**: A list of photos, their resolutions, and the places they represent.

#### 12. List transport services with a bus or train route and their prices
- **Query Purpose**: Uses a UNION to gather transport services that either have a `busRoute` or `trainRoute`, showing their route and price.
- **Expected Results**: Transport options filtered by type (bus or train), with their route and price listed.

---

## 🔧  SWRL Rules
SWRL rules enrich the ontology with implicit logic.

...

## 🧾 Conclusion : Benefits of the Ontology
  The InnovaTrip Ontology provides a structured, semantically rich representation of the tourism domain. By modeling key entities like tourists, guides, service providers, bookings, and media, it enables:
  - Seamless integration and interoperability of heterogeneous tourism data
  - Intelligent querying using SPARQL and rule-based reasoning (SWRL).
  - Enhanced decision-making, search, and personalization features
  - A solid foundation for smart tourism systems such as recommendation engines, trip planners, and semantic web applications.

  This ontology transforms tourism data into machine-understandable knowledge, powering more insightful, flexible, and efficient digital tourism experiences. 🌐✨.

---
**Creators:** Eya SGHAIER & Mohamed Yassine REKIK  
**Date Created:** 01/04/2025  
**Ontology Title:** InnovaTrip Ontology

