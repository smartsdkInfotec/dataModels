# Parking access

## Description

Represents an access point to a parking site, normally an offstreet parking. 

## Data Model

+ `id` : Unique identifier. 

+ `type` : Entity type. It must be equal to `ParkingAccess`.

+ `location` : Geolocation of the access point represented by a GeoJSON Point.
    + Attribute type: `geo:json`.
    + Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    + Mandatory
    
+ `address` : Registered civic address of the access point.
    + Normative References: [https://schema.org/address](https://schema.org/address)
    + Optional

+ `name` : Name given to the access point.
    + Normative References: [https://schema.org/name](https://schema.org/name)
    + Optional

+ `description` : Description of the access point. 
    + Normative References: [https://schema.org/description](https://schema.org/description)
    + Optional

+ `category` : Category of the access point (entrance, exit, etc.)
    + Attribute type: List of [https://schema.org/Text](https://schema.org/Text)
    + Allowed values: Those specificed by the DATEX II *AccessCategoryEnum*.
        + Other values meaningful to the application.
    + Mandatory

+ `refOffStreetParking` : The offstreet parking site this access point gives access to.
    + Attribute type: Reference to an entity of type [OffStreetParking](../../OffStreetParking/doc/spec.md)
    + Mandatory
    
+ `features` : Equipment or facilities provided by the access point.
    + Attribute type: List of [https://schema.org/Text](https://schema.org/Text)
    + Allowed values: Those specified by the DATEX II *AccessEquipmentEnum* and by *AccessibilityEnum*.
        + Other values meaningful to the application.
    + Optional
    
+ `image` : A URL containing a photo of this access point.
    + Normative References: [https://schema.org/image](https://schema.org/image)
    + Optional
    
+ `width` : Width of the access point.
    + Normative References: [https://schema.org/width](https://schema.org/width)
    + Optional
    
+ `height` : Height of the access point.
    + Normative References: [https://schema.org/height](https://schema.org/height)
    + Optional
    
+ `slope` : Slope of the access point (in relative terms).
    + Attribute Type: [Number](https://schema.org/Number)
    + Attribute Value: A number between 0 and 1.
    + Optional
  
  ## Examples of use
  
    {
      "id": "accesspoint-trinidade-1",
      "type": "ParkingAccess",
      "name": "Trinidade main entrance",
      "location": {
        "coordinates": [-8.60961198807, 41.150691773],
        "type": "Point"
      },
      "category": ["vehicleEntrance"],
      "refOffStreetParking": "porto-OffStreetParking-23889",
      "features": ["barrier"]
    }
  
  ## Test it with a real service
  
  
  ## Open issues
  