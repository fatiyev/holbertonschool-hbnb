**Detailed Class Diagram for Business Logic Layer**

## **Overview**
This document presents a detailed class diagram for the **Business Logic Layer** of the HBnB Evolution application. It describes the core entities, their attributes, methods, and relationships, ensuring clarity in system design.

## **Entities and Relationships**

### **1. User Entity**
- Attributes:
  - `id: UUID`
  - `first_name: String`
  - `last_name: String`
  - `email: String`
  - `password: String`
  - `is_admin: Boolean`
  - `created_at: DateTime`
  - `updated_at: DateTime`
- Methods:
  - `register() : void`
  - `update_profile() : void`
  - `delete_user() : void`

### **2. Place Entity**
- Attributes:
  - `id: UUID`
  - `title: String`
  - `description: String`
  - `price: Float`
  - `latitude: Float`
  - `longitude: Float`
  - `owner: User`
  - `_reviews: List`
  - `_amenities: List`
  - `created_at: DateTime`
  - `updated_at: DateTime`
- Methods:
  - `create_place() : void`
  - `update_place() : void`
  - `delete_place() : void`
  - `list_amenities() : List<Amenity>`

### **3. Review Entity**
- Attributes:
  - `id: UUID`
  - `place: Place`
  - `user: User`
  - `rating: Integer`
  - `comment: String`
  - `created_at: DateTime`
  - `updated_at: DateTime`
- Methods:
  - `create_review() : void`
  - `update_review() : void`
  - `delete_review() : void`

### **4. Amenity Entity**
- Attributes:
  - `id: UUID`
  - `name: String`
  - `description: String`
  - `created_at: DateTime`
  - `updated_at: DateTime`
- Methods:
  - `create_amenity() : void`
  - `update_amenity() : void`
  - `delete_amenity() : void`

## **Class Diagram (Mermaid.js Representation)**
[![](https://mermaid.ink/img/pako:eNqtlD9v4zAMxb-KoOn6J8Ot3q4IDuhWtJelMGAQEuMQlSWDkhsEQb77MbbTurFy1yGe5PcoK_w9RnttgkVdaOMgxiVBzdCUXsnTK2oVkdV-UI7P3Wr1uFRkJ8pLYvK1WhPHVHlocO7Jpy5Z2AC5udzK4dvA03MeQnAIXlGswDbkJ9YSEv6hBpVhlKWtIOXcrrVzl7GmmJB_3EzEobJqOazJ4RfLokOxuvi55VD6KbMnBwa_By1RchkoFqNhahOFaZe_XYCkWiaDM9WBfKqzGSP4-tzpQw1bj3wlhsOWqj02nuU4M0aKc8NJGJVMiqdEGC8QfsZ3wu1_EA8x9Cec934Mb6I9-oS1yCwQfT2Pw4RGflC6Lizue8jRyjgjrq_OGZRfPbTd9wYv_2fMz90Vmh0C3eW6zVlju2fWR799hqX-WWq1WMjiVhZD2sVxrOPlqnFwCrVlSjgWDlsvVTIapPd_1p7IF2oDUd_rBlluNSvXap9FqdMGBbcuZGmB30pd-oPUQZfCy84bXSTu8F5z6OqNLtbgorwNfMY7-UNtwb-GcHo__AXQmLW-?type=png)](https://mermaid.live/edit#pako:eNqtlD9v4zAMxb-KoOn6J8Ot3q4IDuhWtJelMGAQEuMQlSWDkhsEQb77MbbTurFy1yGe5PcoK_w9RnttgkVdaOMgxiVBzdCUXsnTK2oVkdV-UI7P3Wr1uFRkJ8pLYvK1WhPHVHlocO7Jpy5Z2AC5udzK4dvA03MeQnAIXlGswDbkJ9YSEv6hBpVhlKWtIOXcrrVzl7GmmJB_3EzEobJqOazJ4RfLokOxuvi55VD6KbMnBwa_By1RchkoFqNhahOFaZe_XYCkWiaDM9WBfKqzGSP4-tzpQw1bj3wlhsOWqj02nuU4M0aKc8NJGJVMiqdEGC8QfsZ3wu1_EA8x9Cec934Mb6I9-oS1yCwQfT2Pw4RGflC6Lizue8jRyjgjrq_OGZRfPbTd9wYv_2fMz90Vmh0C3eW6zVlju2fWR799hqX-WWq1WMjiVhZD2sVxrOPlqnFwCrVlSjgWDlsvVTIapPd_1p7IF2oDUd_rBlluNSvXap9FqdMGBbcuZGmB30pd-oPUQZfCy84bXSTu8F5z6OqNLtbgorwNfMY7-UNtwb-GcHo__AXQmLW-)

## **Explanation of Relationships**
- A **User** can own multiple **Places**.
- A **User** can write multiple **Reviews**.
- A **Place** can receive multiple **Reviews**.
- A **Place** can have multiple **Amenities**.

## **Conclusion**
This detailed class diagram provides a structured overview of the **Business Logic Layer** in HBnB Evolution. The entities, attributes, methods, and relationships ensure modular and scalable development.
