# Introduction

Welcome to the backend API documentation for Wavetags SAAS, the powerful application designed to enhance your digital profile and networking experience.


## API Overview

The Wavetags SAAS Backend API provides seamless integration for managing user profiles, connectivity features, and other functionalities. Below is an overview of the key features available through the API:

- **Profile Customization:** Personalize user profile URLs and generate custom QR codes.
- **Connectivity:** Enable NFC tag integration for seamless profile URL sharing.
- **Business Boost:** Implement branded push notifications and profile themes for businesses.
- **Contact Details:** Manage and share user contact information effortlessly.
- **Social Media Integration:** Integrate with major platforms for a cohesive online presence.
- **Content Showcase:** Control headers, paragraph text, embedded videos, and file uploads.
- **Music Links:** Handle connections to Spotify, Youtube Music, Apple Music, or Soundcloud.
- **Diversified Links:** Manage Discord and Twitch links for versatile connections.
- **Emergency Info:** Implement and retrieve user Medical ID details.
- **Business Lead Collection:** Collect user details through a popup contact form for business profiles.
- **Analytics:** Retrieve insights using Google Analytics.
- **Integration:** Explore third-party integrations like the Amazon Affiliate Store.

## Technologies Used

- Node.js
- Express.js
- MongoDB
- TypeScript
- Swagger

## API Documentation

### API 1: Retreive Insight

- **Endpoint:** `/api/insight/`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve insights for Wavetag.

### API 2: Insight by Card ID and Type

- **Endpoint:** `/api/insight/:card_id/:type`
- **Method:** `PATCH`
- **Parameters:** 
  - `card_id`: [Card ID to identify the Card]
  - `type`: [Type to identify the operation]

- **Description:** Update insights based on card ID and type.

### API 3: Insight by Card ID and Link ID

- **Endpoint:** `/api/insight/tap/:card_id/:link_id`
- **Method:** `PATCH`
- **Parameters:** 
  - `card_id`: [Card ID to identify the Card]
  - `link_id`: [Link ID to identify the Link]
- **Description:** Update insights based on card ID and link ID.

### API 4: Login

- **Endpoint:** `/api/auth/login`
- **Method:** `POST`
- **Parameters:** None
- **Request Body:**
  ```json
  {
    "email": "user@example.com",
    "password": "securepassword"
  }
  ```
- **Description:**  User login.

### API 5: Logout

- **Endpoint:** `/api/auth/logout`
- **Method:** `POST`
- **Parameters:** None
- **Request Headers:**
  - `Authorization`: Bearer [token]
- **Description:**  User logout.

### API 6: Refresh Token

- **Endpoint:** `/api/auth/refresh`
- **Method:** `POST`
- **Parameters:** None
- **Request Headers:**
  - `Authorization`: Bearer [refresh_token]
- **Description:**  Refresh user access token.

### API 7: Retreive User

- **Endpoint:** `/api/users/`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve user information.

### API 8: Create User

- **Endpoint:** `/api/users/`
- **Method:** `POST`
- **Parameters:** None
- **Request Body:**
  ```json
  {
    "username": "example_username",
    "email": "user@example.com",
    "phoneNumber": "1234567890",
    "firstName": "John",
    "lastName": "Doe",
    "password": "securepassword"
  }
  ```
- **Description:** Create a new user

### API 8: Get User by ID

- **Endpoint:** `/api/users/:id`
- **Method:** `GET`
- **Parameters:**
  - `id`: [User ID to identify the user]
- **Description:** Retrieve user information by user ID.

### API 9: Update User by ID

- **Endpoint:** `/api/users/:id`
- **Method:** `PATCH`
- **Parameters:**
  - `userId`: [User ID to identify the user]
- **Request Body:**
  ```json
  {
    "firstName": "NewFirstName",
    "lastName": "NewLastName",
    "email": "new.email@example.com",
    "phoneNumber": "1234567890",
    "userName": "new_username"
  }
  ```

### API 10: Delete User

- **Endpoint:** `/api/users/:id`
- **Method:** `DELETE`
- **Parameters:**
  - `userId`: [User ID to identify the user]
- **Description:** Delete a user by ID.

### API 11: Retreive Link

- **Endpoint:** `/api/links/`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve links information.

### API 12: Create Link

- **Endpoint:** `/api/links/`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "name": "LinkName",
    "link": "https://example.com",
    "icon": "icon-url"
  }
  ```
- **Description:** Create a new link.

### API 13: Get Link Information

- **Endpoint:** `/api/links/:linkId`
- **Method:** `GET`
- **Parameters:**
  - `linkId`: [Link ID to identify the link]
- **Description:** Retrieve information for a specific link by ID.

### API 14: Update Link

- **Endpoint:** `/api/links/:linkId`
- **Method:** `PATCH`
- **Parameters:**
  - `linkId`: [Link ID to identify the link]
- **Request Body:**
  ```json
  {
    "name": "Link Name",
    "link": "https://example.com",
    "icon": "icon_url"
  }
  ```
- **Description:** Update link information by ID.

### API 15: Delete Link

- **Endpoint:** `/api/links/:linkId`
- **Method:** `DELETE`
- **Parameters:**
  - `linkId`: [Link ID to identify the link]
- **Description:** Delete a link by ID.

### API 16: Upload Image

- **Endpoint:** `/api/uploads/image/:imageType`
- **Method:** `POST`
- **Parameters:**
  - `imageType`: [Description]
- **Request Body:**
  Include the image file in the request body.
- **Description:** Upload an image for a specific link type.

### API 17: Get Card

- **Endpoint:** `/api/card/`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve card information.

### API 18: Create Card

- **Endpoint:** `/api/card/`
- **Method:** `POST`
- **Parameters:**
  - `cardTitle`: [Description]
  - `user`: [Description]
  - `theme`: [Description]
  - `layout`: [Description]
  - `qrCode`: [Description]
- **Description:** Create a new card.

### API 19: Get Card by ID

- **Endpoint:** `/api/card/:id`
- **Method:** `GET`
- **Parameters:**
  - `userId`: [User ID to identify the User]
- **Description:** Retrieve card details by ID.

### API 20: Update Card

- **Endpoint:** `/api/card/:id`
- **Method:** `PATCH`
- **Parameters:**
  - `cardId`: [Card ID to identify the Card]
- **Request Body:**
  ```json
  {
    "cardTitle": "New Title",
    "user": "New User",
    "theme": "Updated Theme",
    "layout": "Updated Layout",
    "qrCode": "Updated QR Code"
  }
  ```
- **Description:** Update card details by ID.

### API 21: Delete Card

- **Endpoint:** `/api/card/:id`
- **Method:** `DELETE`
- **Parameters:**
  - `cardId`: [Card ID to identify the Card]
- **Description:** Delete a card by ID.

### API 22: Update Lead Form

- **Endpoint:** `/api/leadForm/:id`
- **Method:** `PATCH`
- **Parameters:**
  - `formId`: [Form ID to identify the Form]
- **Request Body:**
  ```json
  {
    "card_id": "example_card_id",
    "isLeadEnabled": true,
    "header": "New Header",
    "fields": ["field1", "field2"]
  }
  ```
- **Description:** Update a lead form by ID.

### API 23: Get Lead Form

- **Endpoint:** `/api/leadForm/:id`
- **Method:** `GET`
- **Parameters:**
  - `formId`: [Form ID to identify the Form]
- **Description:** Retrieve a lead form by ID.

### API 24: Get Blogs

- **Endpoint:** `/api/blogs/`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve Blog information.

### API 25: Create Blog

- **Endpoint:** `/api/blogs/`
- **Method:** `POST`
- **Parameters:** None
- **Request Body:**
  ```json
  {
    "heading": "Blog Title",
    "blogcontent": "This is the content of the blog.",
    "cardid": "card_id_value",
    "description": "Brief description of the blog.",
    "coverimg": "URL or base64 image data"
  }
  ```
- **Description:** Create a new blog.

### API 26: Get Blog by ID

- **Endpoint:** `/api/blogs/:blogId`
- **Method:** `GET`
- **Parameters:**
  - `blogId`: [Blog ID to identify the blog]
- **Description:** Retrieve a blog by ID.

### API 27: Delete Blog by ID

- **Endpoint:** `/api/blogs/:blogId`
- **Method:** `DELETE`
- **Parameters:**
  - `blogId`: [Blog ID to identify the blog]
- **Description:** Delete a blog by ID.

### API 28: Update Blog

- **Endpoint:** `/api/blogs/:blogId`
- **Method:** `PATCH`
- **Parameters:**
  - `blogId`: [Blog ID to identify the blog]
- **Request Body:**
  ```json
  {
    "heading": "New Blog Heading",
    "blogcontent": "Updated content of the blog",
    "cardid": "updatedCardId",
    "description": "Updated blog description",
    "coverimg": "new_cover_image_url"
  }
  ```
- **Description:** Update a blog by ID.

### API 29: Get Feature Request Settings

- **Endpoint:** `/api/setting/feature-request`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve feature request settings.

### API 30: Submit Feature Request

- **Endpoint:** `/api/setting/feature-request`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "user": "example_user",
    "message": "I would like to request a new feature..."
  }
  ```
- **Description:** Submit a feature request.

### API 31: Support Message

- **Endpoint:** `/api/setting/support-message`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "user": "username",
    "subject": "Message Subject",
    "message": "Detailed support message"
  }
  ```
- **Description:** Send a support message.

### API 32: Get Support Message

- **Endpoint:** `/api/setting/support-message`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve support message settings.

### API 33: Retreive Subscription

- **Endpoint:** `/api/subscription/`
- **Method:** `GET`
- **Parameters:** None
- **Description:** Retrieve subscription information.

### API 34: Create Subscription

- **Endpoint:** `/api/subscription/`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "subscription": "example_subscription",
    "planType": "example_plan",
    "price": 19.99,
    "features": ["feature1", "feature2", "feature3"]
  }
  ```
- **Description:** Create a new subscription.

### API 35: Subscribe User

- **Endpoint:** `/api/subscription/user/:userId/:subscriptionId`
- **Method:** `POST`
- **Parameters:**
  - `userId`: [User ID to identify the user]
  - `subscriptionId`: [Subscription ID to identify the Subscription]
- **Description:** Subscribe a user to a specific subscription.

### API 36: Get User Subscription By ID

- **Endpoint:** `/api/subscription/user/:userId`
- **Method:** `GET`
- **Parameters:**
  - `userId`: [User ID to identify the user]
- **Description:** Retrieve user subscription details by user ID.

### API 37: Create Form Data

- **Endpoint:** `/api/form-data/:leadFormId/:cardId/:userId`
- **Method:** `POST`
- **Parameters:**
  - `leadFormId`: [Lead Form ID to identify the Lead Form]
  - `cardId`: [Card ID to identify the Card]
  - `userId`: [User ID to identify the user]
- **Request Body:**
  ```json
  {
    "formData": { ... }
  }
  ```
- **Description:** Save form data associated with a lead form, card, and user.

### API 38: Get Form Data

- **Endpoint:** `/api/form-data/:leadFormId`
- **Method:** `GET`
- **Parameters:**
  - `leadFormId`: [Lead Form ID to identify the Lead Form]
- **Description:** Retrieve form data by lead form ID.


## MongoDB Schemas

### Schema 1: User

The `User` schema defines the structure of user data within the application.

- **username**: String
  - **Description**: User's username.
  - **Type**: String
  - **Required**: Yes
  - **Unique**: Yes
  - **Indexed**: Yes

- **email**: String
  - **Description**: User's email address.
  - **Type**: String
  - **Required**: Yes
  - **Unique**: Yes
  - **Indexed**: Yes

- **phoneNumber**: String
  - **Description**: User's phone number.
  - **Type**: String
  - **Required**: Yes
  - **Unique**: Yes
  - **Indexed**: Yes

- **firstName**: String
  - **Description**: User's first name.
  - **Type**: String
  - **Required**: Yes
  - **Default**: ''

- **lastName**: String
  - **Description**: User's last name.
  - **Type**: String
  - **Required**: Yes
  - **Default**: ''

- **password**: String
  - **Description**: User's password.
  - **Type**: String
  - **Required**: Yes
  - **Default**: null

- **QrCode**: String
  - **Description**: User's QR code.
  - **Type**: String
  - **Default**: null

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the user.
  - **Type**: Boolean
  - **Default**: true

### Schema 2: Blog

The `Blog` Schema Manages blog posts including headings, content, associated card IDs, descriptions, and cover images.

- **heading**: String
  - **Description**: Heading of the blog.
  - **Type**: String
  - **Required**: Yes
  - **Indexed**: Yes

- **blogcontent**: String
  - **Description**: Content of the blog.
  - **Type**: String
  - **Required**: Yes

- **cardid**: String
  - **Description**: Identifier of the associated card.
  - **Type**: String
  - **Required**: Yes

- **description**: String
  - **Description**: Description of the blog.
  - **Type**: String
  - **Required**: Yes

- **coverimg**: String
  - **Description**: URL of the cover image for the blog.
  - **Type**: String
  - **Required**: Yes

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the blog.
  - **Type**: Boolean
  - **Default**: true  

### Schema 3: Card

The `Card` Schema Manages user cards, including personal and professional information, social links, and lead generation settings.

- **cardTitle**: String
  - **Description**: Title of the card.
  - **Type**: String
  - **Required**: No

- **user**: ObjectId (ref: 'User')
  - **Description**: References the user who owns the card.
  - **Type**: ObjectId
  - **Required**: Yes

- **hash**: String
  - **Description**: Hash value of the card.
  - **Type**: String
  - **Required**: Yes

- **fields**: Object
  - **Description**: Fields of the card.
  - **Type**: Object
  - **Sub-fields**:
    - **name**: String
      - **Description**: Name of the card owner.
      - **Type**: String
      - **Default**: ''
    - **title**: String
      - **Description**: Title of the card owner.
      - **Type**: String
      - **Default**: ''
    - **company**: String
      - **Description**: Company name of the card owner.
      - **Type**: String
      - **Default**: ''
    - **address**: String
      - **Description**: Address of the card owner.
      - **Type**: String
      - **Default**: ''
    - **bio**: String
      - **Description**: Bio of the card owner.
      - **Type**: String
      - **Default**: ''

- **layout**: String
  - **Description**: Layout of the card.
  - **Type**: String
  - **Required**: No

- **socialLinks**: Array of Objects
  - **Description**: Social links associated with the card.
  - **Type**: Array
  - **Object Structure**:
    - **link**: ObjectId (ref: 'Link')
      - **Description**: References a social link.
      - **Type**: ObjectId

- **profilePicture**: String
  - **Description**: URL of the card owner's profile picture.
  - **Type**: String
  - **Required**: No
  - **Default**: ''

- **coverPicture**: String
  - **Description**: URL of the card's cover picture.
  - **Type**: String
  - **Required**: No
  - **Default**: ''

- **companyLogo**: String
  - **Description**: URL of the card owner's company logo.
  - **Type**: String
  - **Required**: No
  - **Default**: ''

- **qrCode**: String
  - **Description**: URL of the card's QR code.
  - **Type**: String
  - **Required**: Yes

- **isLeadEnabled**: Boolean
  - **Description**: Indicates whether lead generation is enabled for the card.
  - **Type**: Boolean
  - **Required**: No
  - **Default**: false

- **lead**: ObjectId (ref: 'LeadForm')
  - **Description**: References the lead form associated with the card.
  - **Type**: ObjectId
  - **Required**: No

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the card.
  - **Type**: Boolean
  - **Default**: true

### Schema 4: FeatureRequest

The `FeatureRequest` Schema Manages feature requests submitted by users.

- **user**: ObjectId (ref: 'User')
  - **Description**: References the user who submitted the feature request.
  - **Type**: ObjectId
  - **Required**: Yes
  - **Indexed**: Yes

- **message**: String
  - **Description**: Message containing the feature request.
  - **Type**: String
  - **Required**: Yes

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the feature request.
  - **Type**: Boolean
  - **Default**: true

### Schema 5: FormData

The `FormData` Schema Stores form data associated with lead forms.

- **leadForm**: ObjectId (ref: 'LeadForm')
  - **Description**: References the lead form associated with the form data.
  - **Type**: ObjectId
  - **Required**: Yes

- **data**: Array of ObjectId (ref: 'FormFields')
  - **Description**: References the form fields data associated with the form.
  - **Type**: Array

### Schema 6: Insight

The `Insight` Schema Tracks insights such as leads generated, link taps, card views, and contacts downloaded.

- **cardId**: ObjectId (ref: 'Card')
  - **Description**: References the card associated with the insight.
  - **Type**: ObjectId
  - **Required**: Yes

- **numberOfLeadGenerated**: Number
  - **Description**: Number of leads generated.
  - **Type**: Number
  - **Default**: 0

- **numberOfLinkTaps**: Number
  - **Description**: Number of link taps.
  - **Type**: Number
  - **Default**: 0

- **numberOfCardViews**: Number
  - **Description**: Number of card views.
  - **Type**: Number
  - **Default**: 0

- **numberOfContactsDownload**: Number
  - **Description**: Number of contacts downloaded.
  - **Type**: Number
  - **Default**: 0

- **leads**: Array of Objects
  - **Description**: Leads associated with the insight.
  - **Type**: Array
  - **Object Structure**:
    - **id**: ObjectId (ref: 'FormData')
      - **Description**: References the form data associated with the lead.
      - **Type**: ObjectId
    - **time**: Date
      - **Description**: Time when the lead was generated.
      - **Type**: Date
      - **Default**: Current timestamp
    - **locationFromIp**: String
      - **Description**: Location inferred from the IP address of the lead.
      - **Type**: String

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the insight.
  - **Type**: Boolean
  - **Default**: true

### Schema 7: LeadForm

The `LeadForm` Schema Manages lead forms with customizable fields.

- **header**: String
  - **Description**: Header for the lead form.
  - **Type**: String
  - **Required**: No

- **fields**: Array of Objects
  - **Description**: Fields of the lead form.
  - **Type**: Array
  - **Object Structure**:
    - **fieldType**: String
      - **Description**: Type of field.
      - **Type**: String
    - **label**: String
      - **Description**: Label for the field.
      - **Type**: String
    - **isEnabled**: Boolean
      - **Description**: Whether the field is enabled.
      - **Type**: Boolean
    - **isRequired**: Boolean
      - **Description**: Whether the field is required.
      - **Type**: Boolean
    - **placeholder**: String
      - **Description**: Placeholder text for the field.
      - **Type**: String
    - **options**: Array of Objects
      - **Description**: Options for the field (if applicable).
      - **Type**: Array
      - **Object Structure**:
        - **label**: String
          - **Description**: Label for the option.
          - **Type**: String
        - **value**: String
          - **Description**: Value of the option.
          - **Type**: String

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the lead form.
  - **Type**: Boolean
  - **Default**: true

### Schema 8: Link

The `Link` Schema Manages links with associated names and icons.

- **name**: String
  - **Description**: Name of the link.
  - **Type**: String
  - **Required**: Yes
  - **Indexed**: Yes

- **link**: String
  - **Description**: URL of the link.
  - **Type**: String
  - **Required**: Yes

- **icon**: String
  - **Description**: Icon associated with the link.
  - **Type**: String
  - **Required**: Yes

### Schema 9: Subscription

The `Subscription` Schema Manages subscription plans for users.

- **subscription**: String
  - **Description**: Type of subscription plan.
  - **Type**: String
  - **Default**: 'FREE'
  - **Enum**: [List of available subscription plans]

- **planType**: String
  - **Description**: Type of subscription plan.
  - **Type**: String
  - **Required**: Yes

- **price**: Number
  - **Description**: Price of the subscription plan.
  - **Type**: Number
  - **Required**: Yes

- **features**: Array of Strings
  - **Description**: Features included in the subscription plan.
  - **Type**: Array
  - **Default**: []
  
- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the subscription.
  - **Type**: Boolean
  - **Default**: true

### Schema 10: SupportMessage

The `SupportMessage` Schema Manages support messages sent by users.

- **user**: ObjectId (ref: 'User')
  - **Description**: References the user who sent the support message.
  - **Type**: ObjectId
  - **Required**: Yes
  - **Indexed**: Yes

- **subject**: String
  - **Description**: Subject of the support message.
  - **Type**: String
  - **Required**: Yes

- **message**: String
  - **Description**: Content of the support message.
  - **Type**: String
  - **Required**: Yes

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the support message.
  - **Type**: Boolean
  - **Default**: true


### Schema 11: Theme

The `Theme` Schema Manages themes for the application.

- **name**: String
  - **Description**: Name of the theme.
  - **Type**: String
  - **Required**: Yes

- **themeId**: String
  - **Description**: Identifier for the theme.
  - **Type**: String
  - **Required**: Yes

### Schema 12: UserProfile

The `UserProfile` schema defines the structure of user profiles within the application.

- **profilePicture**: String
  - **Description**: URL of the user's profile picture.
  - **Type**: String
  - **Required**: Yes
  - **Indexed**: Yes

- **user**: ObjectId (ref: 'User')
  - **Description**: References the user associated with the profile.
  - **Type**: ObjectId
  - **Required**: Yes
  - **Indexed**: Yes

- **address**: Object
  - **lat**: Number
    - **Description**: Latitude of the user's address.
    - **Type**: Number
    - **Required**: Yes
  - **lon**: Number
    - **Description**: Longitude of the user's address.
    - **Type**: Number
    - **Required**: Yes
  - **address**: String
    - **Description**: Address of the user.
    - **Type**: String
    - **Required**: Yes

- **bio**: String
  - **Description**: Biography of the user.
  - **Type**: String
  - **Required**: Yes

- **theme**: ObjectId (ref: 'Theme')
  - **Description**: References the theme selected by the user.
  - **Type**: ObjectId
  - **Required**: Yes

- **coverpicture**: String
  - **Description**: URL of the user's cover picture.
  - **Type**: String
  - **Required**: Yes

- **cardTitle**: String
  - **Description**: Title of the user's card.
  - **Type**: String
  - **Required**: Yes

### Schema 13: UserLinkType

The `UserLinkType` schema represents the relationship between a user and their associated links.

- **user**: ObjectId (ref: 'User', required: true, index: true)
  - **Description**: References the user associated with the links.
  - **Type**: ObjectId
  - **Required**: Yes
  - **Indexed**: Yes

- **links**: Array
  - **subLink**: String (required: true)
    - **Description**: Sublink associated with the link.
    - **Type**: String
    - **Required**: Yes
  - **link**: ObjectId (ref: 'Link', required: true)
    - **Description**: References the link.
    - **Type**: ObjectId
    - **Required**: Yes

### Schema 14: UserSubscription

The `UserSubscription` schema represents the relationship between a user and their subscription within the application.

- **subscription**: ObjectId (ref: 'Subscription', required: true, index: true)
  - **Description**: References the subscription associated with the user subscription.
  - **Type**: ObjectId
  - **Required**: Yes
  - **Indexed**: Yes

- **user**: ObjectId (ref: 'User', required: true, index: true)
  - **Description**: References the user associated with the user subscription.
  - **Type**: ObjectId
  - **Required**: Yes
  - **Indexed**: Yes

- **timestamps**: Boolean
  - **Description**: Automatically tracks the creation and modification timestamps of the user subscription.
  - **Type**: Boolean
  - **Default**: true

## Status Codes

Wavetags returns the following status codes in its API:

| Status Code | Description |
| :--- | :--- |
| 200 | `OK` |
| 201 | `CREATED` |
| 400 | `BAD REQUEST` |
| 404 | `NOT FOUND` |
| 500 | `INTERNAL SERVER ERROR` |

