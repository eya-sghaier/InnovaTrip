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

### Partie1: Version ancienne (Il ya une deuxiéme partie as dessous plus récente)


#### 🔷 Main Classes

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

#### 🧬 Data Properties

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
| ` exhibitionType`   |Museum                             | xsd:string      | Type of an exhibition                       |
| ` facilities`       |Beach                              | xsd:string      | Facilities of the Beach                     |
| ` openingHours`     |Attraction,Pa,Bea,Mus,Monum        | xsd:string      | Hours of Openings                           |
| ` name`             |Place                              | xsd:string      | Name of a Place                             |
| ` location`         |Accommodation                      | xsd:string      | Location of an accommodation                |
| ` historicalSignif` |Place                              | xsd:string      | The historical significance of a Monument   |

---

#### 🔗 Object Properties

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


### Partie 2:


#### Main Changes:

    🟢 Omitted Person superclass
    🟢 Defined: Guide ≡ ServiceProvider ⊓ guidesActivity some Activity
        ✅ Added: Guide ≡ ServiceProvider ⊓ worksAt some Attraction
            Guide ≡ ServiceProvider 
            ⊓ guidesActivity some Activity 
            ⊓ worksAt some Attraction
    🟢 Defined: Attraction ≡ NaturalAttraction ⊔ CulturalAttraction
    🟢 Changed Park to Mountain
    🟢 Defined: CulturalActivity ≡ Activity ⊓ takesPlaceAt some CulturalAttraction
    🟢 Defined: OutdoorActivity ≡ Activity ⊓ takesPlaceAt some NaturalAttraction
    🟢 Declared: DisjointClasses(Hotel, Hostel, GuestHouse)
    🟢 Defined: AttractionReview ≡ Review ⊓ reviewedBy some Activity
    🟢 Defined: AccommodationReview ≡ Review ⊓ reviewedBy some Accommodation
    🟢 Defined: Media ≡ Photo ⊔ Video
    🟢 Added: Private ≡ Transport ⊓ usedExclusivelyBy some Tourist
    🟢 Disjoint: Tourist ⊥ ServiceProvider
    🟢 Disjoint: Public ⊥ Private  (Transport)

    🟢 Defined: AccommodationBooking ≡ Booking ⊓ refersTo only Accommodation 
    🟢 Defined: ActivityBooking ≡ Booking ⊓ refersTo only Activity 
    🟢 Added under Place: TransportHub
    🟢 Defined Driver ≡ ServiceProvider ⊓ worksAt some TransportHub

    🟢 Removed: booksAccommodation
    🟢 Added: refersTo 
        Domain: Booking
        Range: Accommodation ⊔ Activity ⊔ Attraction
    🟢 Removed: reserves   (refersTo took its place)
    🟢 Added: usedExclusivelyBy
        Domain: Transport
        Range: ServiceProvider ⊔ Tourist
    🟢 Added: hasAuthor
        Inverse of: writesReview
        Domain: Review
        Range: Tourist
    🟢 Added: worksAt
        Domain: ServiceProvider
        Range: Place
    🟢 Added: reviewedBy
        Domain: Attraction ⊔ Accommodation 
        Range: Tourist
    🔁 name → hasName	
    🔁 location → hasLocation	
    🔁 historicalSignif        domain: Monument → Place	
    🔁 openingHours → hasOpeningHours	
    🔁 languagesSpoken   domain: Guide → ServiceProvider	
    🗑️ Removed museumName	
    🔁 duration → hasDuration	
    🗑️ Removed areaSize	
    🔁 facilities → hasFacilities	
    🔁 bookingDate → hasBookingDate	.
    🔁 mediaURL → hasMediaURL	
    ➕ Added isPetFriendly (Accommodation, xsd:boolean)



#### 🔷 Main Classes

│ Tourist

│ ServiceProvider               
├── Driver                      
└── Guide                       

Place
├── Attraction                  
│   ├── NaturalAttraction      
│   │   ├── Beach
│   │   └── Mountain
│   └── CulturalAttraction     
│       ├── Museum
│       └── Monument
├── TransportHub
├── City
└── Country

Activity
├── CulturalActivity
│   ├── MuseumVisit
│   └── HeritageTour
└── OutdoorActivity
    ├── Hiking
    └── Diving

Accommodation
├── Hotel
├── Hostel
└── GuestHouse

Booking
├── AccommodationBooking
├── ActivityBooking


Review
├── AttractionReview
├── AccommodationReview   

Media
├── Photo
└── Video

Transport
├── Private
│   ├── Taxi
│   └── CarRental
└── Public
    ├── Bus
    └── Train


#### 🔗 Object Properties

| Property               | Domain    | Range         | Description                                           |                  |
|------------------------|------------|---------------|-------------------------------------------------------|-----------------|
| `bookingMadeBy`        | Booking    | Tourist       | A tourist makes a booking                             |
| `guidesActivity`       | Guide      | Activity      | A guide is responsible for an activity                |
| `hasAttraction`        | Place      | Attraction    | A place includes or features an attraction            |
| `hasAuthor`            | Review     | Tourist       | A review written by a Tourist                         |InverseOf  `writesReview`|
| `hasMedia`             | Media      | Attraction    | Media is associated with an attraction                |
| `participatesIn`       | Tourist    | Activity      | A tourist participates in an activity                 |
| `refersTo`             | Booking    | Accommodation or Activity or Attractiont | A booking refers to a Accommodation or Activity|
| `reviewsAccommodation` | Tourist    | Accommodation | A review evaluates an accommodation                   |
| `reviewsAttraction`    | Tourist    | Attraction    | A review evaluates an attraction                      |
| `takesPlaceAt`         | Activity   | Place         | An activity takes place at a specific place           |
| `usedExclusivelyBy`    | Transport  | ServiceProvider or Tourist | A Transport used by ServiceProvider or Tourist|
| `usesTransport`        | Tourist    | Transport     | A tourist uses a transport service                    |
| `worksAt`              | ServiceProvider    | Place | A booking refers to a Accommodation or Activity       |
| `writesReview`         | Tourist    | Review        | A tourist writes a review                             |InverseOf  `hasAuthor`|
| `reviewedBy`    | Accommodation or Attraction    | Tourist    | A review by Tourist evaluates an attraction or accommodation        |

---
#### 🧬 Data Properties

| Property            | Domain(s)                         | Range           | Description                                 |
|---------------------|-----------------------------------|-----------------|---------------------------------------------|
| ` age`              | Tourist ,Guide, ServiceProvider   | xsd:integer     | Age of the tourist                          |
| ` nationality`      | Tourist                           | xsd:string      | Nationality of the tourist                  |
| ` experienceYears`  | Guide                             | xsd:integer     | Number of years of guiding experience       |
| ` languagesSpoken`  | ServiceProvider                   | xsd:string      | Languages spoken by the guide               |
| ` rating`           | ServiceProvider, Review           | xsd:float       | Assigned rating for the provider            |
| ` companyName`      | ServiceProvider                   | xsd:string      | Name of the service provider's company      |
| ` difficultyLevel`  | Hiking                            | xsd:string      | Level of difficulty of the hiking trail     |
| ` depthLevel`       | Diving                            | xsd:int         | Depth level of the diving activity          |
| ` tourType`         | HeritageTour                      | xsd:string      | Type of heritage tour                       |
| ` price`            | Trans,Booking, Attr,Accommodation | xsd:float       | Price of the service or booking             |
| ` busRoute`         | Bus                               | xsd:string      | Bus route name or number                    |
| ` trainRoute`       | Train                             | xsd:string      | Train route name or number                  |
| ` availableSeats`   | Taxi                              | xsd:int         | Number of available seats in the taxi       |
| ` carModel`         | CarRental                         | xsd:string      | Model of the rented car                     |
| ` hasBookingDate`   | Booking                           | xsd:date        | Date the booking was made                   |
| ` reviewText`       | Review                            | xsd:string      | Content of the review                       |
| ` reviewDate`       | Review                            | xsd:date        | Date the review was written                 |
| ` hasMediaURL`      | Media                             | xsd:string      | Media link (URL)                            |
| ` imageResolution`  | Photo                             | xsd:string      | Resolution of the image                     |
| ` videoDuration`    | Video                             | xsd:int         | Duration of the video in seconds            |
| ` capacity`         |Accommodation                      | xsd:int         | Capacity of an accommodation                |
| ` hasDuration`      |Activity                           | xsd:int         | Duration of an activity                     |
| ` exhibitionType`   |Museum                             | xsd:string      | Type of an exhibition                       |
| ` hasFacilities`    |Beach                              | xsd:string      | Facilities of the Beach                     |
| ` hasOpeningHours`     |Attraction,Pa,Bea,Mus,Monum     | xsd:string      | Hours of Openings                           |
| ` hasName`             |Place or Accommodation          | xsd:string      | Name of a Place                             |
| ` hasLocation`         |Accommodation                   | xsd:string      | Location of an accommodation                |
| ` historicalSignif` |Place                              | xsd:string      | The historical significance of a Place   |
| ` isPetFriendly`    |Accommodation                      | xsd:boolean      | The Accommodation allows pets or not   |

---

## 📑 Description of SPARQL Queries and Their Meaning

This section explains each SPARQL query used in the `InnovaTrip` ontology project, what it is designed to retrieve, and what kind of results it should produce.

---

#### 🟢 Simple SPARQL Queries

##### 1. Get all tourists' names
- **Query Purpose**: Retrieves all individuals of type `Tourist` and their names using the `foaf:name` property.
- **Results**: A list of tourists with their associated names.

##### 2. Get all bookings and their prices
- **Query Purpose**: Retrieves every `Booking` and its corresponding `price`.
- **Results**: A table with bookings and their associated price values.

##### 3. Get all reviews with their text
- **Query Purpose**: Fetches all `Review` instances and displays the written content (`reviewText`).
- **Results**: A list of reviews and the text written by tourists.

##### 4. Get all media and their URLs
- **Query Purpose**: Lists all media elements (images, videos, etc.) and their associated URLs.
- **Results**: A list of media entries with their respective media URLs.

##### 5. Get all transport services and their prices
- **Query Purpose**: Filters transport services like Bus, Train, Taxi, and CarRental and shows their prices.
- **Results**: A table with transport types and their prices.

##### 6. Get all bookings and their dates
- **Query Purpose**: Displays each booking and the corresponding date of the reservation.
- **Results**: A list of bookings along with their booking dates.

##### 7. Get all service providers with their ratings
- **Query Purpose**: Lists all individuals or entities that are `ServiceProvider`s with their given `rating`.
- **Results**: A table of service providers and how they are rated.

##### 8. Find tourists who are younger than 30
- **Query Purpose**: Filters tourists whose `age` is less than 30.
- **Results**: A list of younger tourists with their age displayed.

---

#### 🔷 More Complex SPARQL Queries

##### 9. Find service providers with a rating greater than 4
- **Query Purpose**: Selects highly-rated service providers by applying a filter on `rating`.
- **Results**: Providers with a rating higher than 4, sorted from highest to lowest.

##### 10. Get the name and nationality of tourists younger than 30 and from French nationality
- **Query Purpose**: Retrieves `foaf:name` and `nationality` for tourists who are French and under 30 years old.
- **Results**: A refined list showing French tourists below 30, with their names and nationality.

##### 11. List all photos with their resolution and the place they describe
- **Query Purpose**: Displays all `Photo` instances with their `imageResolution` and the `Place` they are linked to via `mediaOf`.
- **Results**: A list of photos, their resolutions, and the places they represent.

##### 12. List transport services with a bus or train route and their prices
- **Query Purpose**: Uses a UNION to gather transport services that either have a `busRoute` or `trainRoute`, showing their route and price.
- **Results**: Transport options filtered by type (bus or train), with their route and price listed.

---

## 🔧  SWRL Rules
SWRL rules enrich the ontology with implicit logic.

### ✅ 1. 🧓 Rule for SeniorGuide
If a Guide has more than 20 years of experience, classify them as a SeniorGuide.

**Explanation**: Adds experienced guides automatically to the SeniorGuide class.

Guide(?g) ^ experienceYears(?g, ?y) ^ swrlb:greaterThan(?y, 20) → SeniorGuide(?g)


### ✅ 2. 🐶 Rule for PetLoverTourist
If a Tourist books accommodation that allows pets, they are considered a PetLoverTourist.

**Explanation**: Uses  object properties refersTo and bookingMadeBy, and data property isPetFriendly.

Booking(?b) ^ bookingMadeBy(?b, ?t) ^ refersTo(?b, ?a) ^ isPetFriendly(?a, true) → PetLoverTourist(?t)


### ✅ 3. 🈶 Rule for MultilingualProvider
If a ServiceProvider speaks more than one language, they are a MultilingualProvider.

**Explanation**: Uses languagesSpoken, assuming multiple entries indicate multilingualism.

ServiceProvider(?s) ^ languagesSpoken(?s, ?l1) ^ languagesSpoken(?s, ?l2) ^ swrlb:notEqual(?l1, ?l2) → MultilingualProvider(?s)


### ✅ 4. 😁 Rule for SatisfiedTourist
If a Tourist has reviewed an attraction or accommodation with a rating above 4.5, classify them as a SatisfiedTourist.

**Explanation**: Uses reviewedBy, rating, and inferred relationships.

Review(?r) ^ reviewedBy(?r, ?t) ^ rating(?r, ?score) ^ swrlb:greaterThan(?score, 4.5) → SatisfiedTourist(?t)

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
