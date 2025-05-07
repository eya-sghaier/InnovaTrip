
## 📊 SPARQL Queries for InnovaTrip Ontology

This document contains both **simple** and **complex** SPARQL queries for the `InnovaTrip` ontology.  

---

## 📘 Namespaces

```sparql
PREFIX innova: <http://www.semanticweb.org/yassineeya/InnovaTrip#>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
```

---

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
SELECT ?subject ?object
	WHERE { ?subject rdfs:subClassOf ?object }
  
## 🟢 Simple SPARQL Queries

### 1. Get all tourists' names

```sparql
SELECT ?tourist ?name
WHERE {
  ?tourist rdf:type innova:Tourist .
  ?tourist foaf:name ?name .
}
```

---

### 2. Get all bookings and their prices

```sparql
SELECT ?booking ?price
WHERE {
  ?booking a innova:Booking ;
           innova:price ?price .
}
```

---

### 3. Get all reviews with their text

```sparql
SELECT ?review ?text
WHERE {
  ?review a innova:Review ;
          innova:reviewText ?text .
}
```

---

### 4. Get all media and their URLs

```sparql
SELECT ?media ?url
WHERE {
  ?media innova:hasMediaURL ?url .
}
```

---

### 5. Get all transport services and their prices

```sparql
SELECT ?transport ?price
WHERE {
  ?transport a ?type ;
             innova:price ?price .
  FILTER(?type IN (innova:Bus, innova:Train, innova:Taxi, innova:CarRental))
}
```

---

### 6. Get all bookings and their dates

```sparql
SELECT ?booking ?date
WHERE {
  ?booking a innova:Booking ;
           innova:bookingDate ?date .
}
```

---

### 7. Get all service providers with their ratings

```sparql
SELECT ?provider ?rating
WHERE {
  ?provider rdf:type innova:ServiceProvider .
  ?provider innova:rating ?rating .
}
```

---

### 8. Find tourists who are younger than 30

```sparql
SELECT ?tourist ?age
WHERE {
  ?tourist a innova:Tourist ;
           innova:age ?age .
  FILTER (?age < 30)
}
```

---

## 🔷 More Complex SPARQL Queries

### 9. Find service providers with a rating greater than 4

```sparql
SELECT ?serviceProvider ?rating
WHERE {
  ?serviceProvider a innova:ServiceProvider ;
                   innova:rating ?rating .
  FILTER (?rating > 4)
}
ORDER BY DESC(?rating)
```

---

### 10. Get the name and nationality of tourists younger than 30 and from "French" nationality

```sparql
SELECT ?name ?nationality
WHERE {
  ?tourist a innova:Tourist ;
           foaf:name ?name ;
           innova:nationality "French" ;
           innova:age ?age .
  FILTER (?age < 30)
}
```

---

### 11. List all photos with their resolution and the place they describe

```sparql
SELECT ?photo ?place ?resolution
WHERE {
  ?photo a innova:Photo ;
         innova:imageResolution ?resolution ;
         ?place innova:mediaOf  .
}
```

---

### 12. List transport services with a bus or train route and their prices

```sparql
SELECT ?transport ?type ?route ?price
WHERE {
  ?transport a ?type ;
             innova:price ?price .
  {
    ?transport innova:busRoute ?route .
  } UNION {
    ?transport innova:trainRoute ?route .
  }
}
```