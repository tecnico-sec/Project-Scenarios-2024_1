Instituto Superior Técnico, Universidade de Lisboa

**Network and Computer Security**

# Preamble

This document explains the project scenarios.  
Please read the project overview first.

The scenarios describe a richer application context than the one that will be actually need to be implemented.  
The security aspects should be the focus of your work.
User interface design, although critical in a real application, is secondary in this project.

Each project team can change the document format for each scenario, but the fields shown must still be included in some way.

# Project Scenarios

_Congratulations! You have been hired by one of the following companies._

Each company has its business context and, more importantly, a document format that is pivotal for their business.  
Later in the project, a security challenge will be revealed and your team will have to respond to it with a suitable solution.

----

## 1. Retail: GrooveGalaxy

GrooveGalaxy is an online music store that sells songs in a custom format.  
GrooveGalaxy allows users to search and browse through a wide range of songs, artists, and genres.
The ability to preview songs is particularly helpful, ensuring that consumers only purchase music that resonates with them.
Once they decide to buy, the process is seamless, offering choices in file formats like WAV or FLAC, suitable for various devices.  
GrooveGalaxy offers a personal account feature, enabling users to manage their purchases and preferences.
It even tailors music recommendations based on listening history.
This store effectively caters to the needs of music lovers, combining convenience, variety, and personalization.

The core data handled by the store is exemplified next:

```json
{
  "media": {
    "mediaInfo": {
      "owner": "Bob",
      "format": "WAV",
      "artist": "Alison Chains",
      "title": "Man in the Bin",
      "genre": ["Grunge", "Alternative Metal"]
    },
    "mediaContent": {
      "lyrics": [
        "Trapped in a world, a box of my own",
        "Container whispers, in this space alone",
        "Echoes of silence, in the walls I confide",
        "A man in the box, with nowhere to hide",
        "Chained by thoughts, in a silent uproar",
        "Searching for keys, to unlock the door"
      ],
      "audioBase64": "UklGRiQIAAAWQVZAAWQVZFZm10IBAAAAABAAFZm10IBAAAAAAAWQVZFZm10IBAAAWQVZFZm10IBAAAAABAAAAAABAABAAIAEABAAWQVZFZm10IBAAAAABAAHACAAA...ABGAAQAFABkYXRhAAgA=="
    }
  }
}
```

### Protection Needs

The protected document must ensure the _authenticity_ of the song data.  
Additionally, it must also ensure that only the owner can listen to the song, i.e., the content is _confidential_ and accessible only to the owner.  
You can assume that the user and the service share a secret value.

### Security Challenge

(to appear later)

## 2. Restaurants & Tourism: BombAppetit

BombAppetit is a web application tailored to enhance the dining experience.
It simplifies restaurant reservations with an intuitive interface.
Users can explore a curated list of local restaurants based on their location, making it easy to find the perfect dining spot.
BombAppetit facilitates table reservations for any group size.  
The system integrates with a discount card service, allowing patrons to redeem their accumulated points for attractive booking discounts.
BombAppetit revolutionizes dining convenience, connecting users with delightful culinary experiences.

The core data handled by the application is exemplified next:

```json
{
  "restaurantInfo": {
    "owner": "Maria Silva",
    "restaurant": "Dona Maria",
    "address": "Rua da Glória, 22, Lisboa",
    "genre": ["Portuguese", "Traditional"],
    "menu": [
      {
        "itemName": "House Steak",
        "category": "Meat",
        "description": "A succulent sirloin grilled steak.",
        "price": 24.99,
        "currency": "EUR"
      },
      {
        "itemName": "Sardines",
        "category": "Fish",
        "description": "A Portuguese staple, accompanied by potatoes and salad.",
        "price": 21.99,
        "currency": "EUR"
      },
      {
        "itemName": "Mushroom Risotto",
        "category": "Vegetarian",
        "description": "Creamy Arborio rice cooked with assorted mushrooms and Parmesan cheese.",
        "price": 16.99,
        "currency": "EUR"
      }
    ],
    "mealVoucher": {
      "code": "VOUCHER123",
      "description": "Redeem this code for a 20% discount in the meal. Drinks not included."
    }
  }
}
```

### Protection Needs

The protected document must ensure the _authenticity_ of the restaurant data.
If a voucher exists, it should be _confidential_ so that only the user should be able to access it.  
You can assume that the user and the service share their respective public keys.

### Security Challenge

(to appear later)

## 3. Insurance & Banking: BlingBank

BlingBank is a contemporary digital financial platform, built on the principles of accessibility and convenience.
BlingBank provides an online banking platform, accessible via a web application.  
The main functionalities are: account management, expense monitoring, and payments.
The account management allows an efficient oversight of account balance.
Expense monitoring shows the movements corresponding to expenses, in categories.
Finally, payments allow a simple way to make bill payments.

The core data handled by the application is exemplified next:

```json
{
  "account": {
    "accountHolder": ["Alice"],
    "balance": 872.22,
    "currency": "EUR",
    "movements": [
      {
        "date": "09/11/2023",
        "value": 1000.00,
        "description": "Salary"
      },
      {
        "date": "15/11/2023",
        "value": -77.78,
        "description": "Electricity bill"
      },
      {
        "date": "22/11/2023",
        "value": -50.00,
        "description": "ATM Withdrawal"
      }
    ]
  }
}
```

### Protection Needs

The protected document must ensure the _authenticity_ and _confidentiality_ of the account data.  
You can assume that the user and the service share a secret key.

### Security Challenge

(to appear later)

## 4. Healthcare: MediTrack

MediTrack is an Electronic Health Records (EHR) system for managing patient data securely in Portugal's healthcare institutions.
It supports various medical services, including Urgent Care and Specialty Consultations like Orthopedics, Cardiology, and Dermatology.  
This electronic record helps enhance health services and connect with other institutions.
MediTrack is used by Hospitals and Clinics where Doctors add consultation records.

The core data handled by the system is exemplified next:

```json
{
  "patient": {
    "name": "Bob",
    "sex": "Male",
    "dateOfBirth": "2004-05-15",
    "bloodType": "A+",
    "knownAllergies": ["Penicillin"],
    "consultationRecords": [
      {
        "date": "2022-05-15",
        "medicalSpeciality": "Orthopedic",
        "doctorName": "Dr. Smith",
        "practice": "OrthoCare Clinic",
        "treatmentSummary": "Fractured left tibia; cast applied."
      },
      {
        "date": "2023-04-20",
        "medicalSpeciality": "Gastroenterology",
        "doctorName": "Dr. Johnson",
        "practice": "Digestive Health Center",
        "treatmentSummary": "Diagnosed with gastritis; prescribed antacids."
      },
      {
        "date": "2023-09-05",
        "medicalSpeciality": "Dermatology",
        "doctorName": "Dr. Martins",
        "practice": "SkinCare Clinic",
        "treatmentSummary": "Treated for Molluscum Contagiosum; prescribed topical corticosteroids."
      }
    ]
  }
}
```

### Protection Needs

The protected document must ensure the _authenticity_ and _confidentiality_ of the patient data and metadata.  
You can assume that the user and the service share public keys.

### Security Challenge

(to appear later)

----

[SIRS Faculty](mailto:meic-sirs@disciplinas.tecnico.ulisboa.pt)
