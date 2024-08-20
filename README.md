<h1 align="center">
  <br>
  <a href="https://github.com/Amir-Battal">
    <img src="https://cdn.worldvectorlogo.com/logos/typescript.svg" alt="ُTypeScript" width="200">
    <img src="https://adware-technologies.s3.amazonaws.com/uploads/technology/thumbnail/20/express-js.png" alt="express.js" width="200">
  </a>
  <br>
  Order App // Backend
  <br>
</h1>

  <h4 align="center">This project is related to the Project tutorial from <a href="https://www.youtube.com/@ChrisBlakely" target="_blank">Chris Blakely</a>.</h4>
<h4 align="center"><span>NOTE: </span>But everything was written by me and I got the general idea from this video.</h4>

<div align="center">

  ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
  ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
  ![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
  ![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB)
  ![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white)
</div>

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#api-reference">API Reference</a> •
  <a href="#run-locally">Run Locally</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#credits">Credits</a> •
  <a href="#license">License</a>
</p>


## Key Features

* Landing Page:
  - Navbar Contains:
      - Logo on the left.
      - If the user is logged in, the user’s email will appear, and next to it, a button called “Order Status” will take the user to a page containing all the orders that the user has requested.
      - Otherwise, a login button will appear.
  - Hero in the next section containes food image.
  - At the bottom of Hero there is a search box, Search for the restaurant by city or town name, and include reset button.
  - Below the above is a picture and a simple explanation of the program and how to download it.
  - At the end of this page there is a footer containing the application logo on the left and the terms and privacy on the right.


* Login & SignUp:
  - A third party, <a href="https://auth0.com/" target="_blank">Auth0</a>, was used.
  - Sign up Using Email or Google Accout.
  - If the user is already registered, he can log in.
  - The authId, and email is stored in the MongoDB database.


* User Profile:
  - On this page there are fields for:
    - Email
    - Name
    - Address Line 1
    - City
    - Country
  - The user can add or modify the following fields: Name, Address Line 1, City, Country.
  - and he can't modify Email.
 
 
* Restaurants Page: After searching using the name of the city or town
  - Left section:
    - Filter by restaurant cuisine in the form of a list.
    - 7 cuisine are displayed and there is a Show More button to view more cuisine.
    - There is a button to reset the filter.
  - Right section:
    - At the top is a box to search for a restaurant using cuisines or the restaurant name, and include a reset button.
    - Below it is the number of restaurants that were searched for by city name at the beginning.
    - and it can be cahnge during the second search by restaurant cusinine.
    - There is a link named "Change Location" go to Home page (first search).
    - On the right side of this section there is a button to sort by Best match, Delivery price, Estimated delivery time.
    - Below the above are restaurant cards that contain:
      - The left side of the card contains a picture of the restaurant.
      - The middle section of the card contains the name of the restaurant and the restaurant's cuisine.
      - The right section of the card contains the estimated delivery time and delivery price.
    - This section contains Pagination feature:
      - Only the first 10 restaurants appear, and at the bottom there are numbers to show other restaurants.
  

* Restaurant Page: After selecting a specific restaurant
  - At first, the restaurant image appears.
  - Below is the restaurant's name, address and cuisines.
  - At the bottom of the restaurant name there is a menu, list of the restaurant's items and the price of each one.
  - To the right of the above there is a card where the items selected by the user are placed, contains:
    - Above is the Total amount of order for all items plus Delivery price.
    - Each item is listed with its own number and price.
    - Each selected item can be deleted.
    - There is also a delivery price.
    - At the bottom there is a button to go to checkout


* Checkout:
  - A third party, <a href="https://stripe.com/" target="_blank">Stripe</a>, was used.
  - The total price is sent to this party.
  - Before payment, the order status must be in the placed state.
  - After successful payment, the order status will be changed to paid but it is called Awaiting Restaurant Confirmation in the Order Status page.

 
* Manage Restaurant section contains two sections:
  - First section: Manage Restuarant:
    - Add and Modify user's restaurant.
    - Restaurant Details is:
      - Restaurant Name
      - Restaurant Address: City, Country
      - Delivery Price from this Restaurant in (£)
      - Estimated Delivery Time From this Restaurant in minutes
      - Restaurant Food Cuisines (Select multiple options)
      - Restaurant Menu: add Name, and Price in (£) for each item, and user can remove any item.
      - Restaurant Image
        
  - Second section: Orders:
    - Active Orders Counter.
    - A card for each order placed from the user's restaurant, contains:
      - Card Header contains: Customer Name, Delivery Address, Time, Total Cost.
      - List of items and their number.
      - Order Status It can be controlled by the restaurant owner user contains many Select multiple options.


* Order Status: User order from multiple restaurants
  - User order card from multiple restaurants, contains:
    - Card Header containes: The order status is selected by the restaurant owner, Estimated delivery time.
    - Progress Bar It is filled based on the status of the request.
    - Delivery to, contains: Address Line 1, City, Country.
    - Your Order, Items selected by the user
    - On the right side there is a picture of the restaurant.
    - At the end there is the total amount including the delivery price and the price of the items.
   

## API Reference

#### User API's
#### Get current user

```http
  GET /api/my/user
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Create new user

```http
  POST /api/my/user
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. user data form |

#### Update user

```http
  PUT /api/my/user
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. use data form |


<br />

#### User Restaurant API's
#### Get current user

```http
  GET /api/my/restaurant
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Create new restaurant

```http
  POST /api/my/restaurant
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. restaurant data form |

#### Update restaurant

```http
  PUT /api/my/restaurant
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. restaurant data form |

#### Get user's restaurant orders

```http
  GET /api/my/restaurant/order
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Update user's restaurant order status

```http
  PATCH /api/my/restaurant/order/${orderId}/status
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |
| `orderId` | `string` | **Required**. OrderId |


#### Restaurants API's
#### Get specific restaurant

```http
  GET /api/restaurant/${restaurantId}
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |
| `restaurantId` | `string` | **Required**. Specific RestaurantId |

#### Search Restaurant

```http
  GET /api/restaurant/search/${city}?${params}
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |
| `city` | `string` | **Required**. Specific City |
| `params` | `string` | **Required**. Specific cuisine or name |

#### Order API's
#### Get user orders

```http
  GET /api/order
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Create checkout session

```http
  POST /api/order/checkout/create-checkout-session
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |



## Run Locally

Clone the project

```bash
  git clone https://github.com/Amir-Battal/mern-order-app-backend.git
```

Go to the project directory

```bash
  cd backend
```

Install dependencies

```bash
  npm install
```

To run this project, you will need to add the following environment variables to your .env file

MongoDB Variable
`MONGODB_CONNECTION_STRING`

Auth0 Variables
`AUTH0_AUDIENCE`
`AUTH0_ISSURE_BASE_URL`

Cloudinary Variables
`CLOUDINARY_CLOUD_NAME`
`CLOUDINARY_API_KEY`
`CLOUDINARY_API_SECRET`

Stripe Variables
`FRONTEND_URL`
`STRIPE_API_KEY`
`STRIPE_WEBHOOK_SECRET`

Example
```bash
# MongoDB
MONGODB_CONNECTION_STRING=mongodb://localhost:27017/mern-order-app

# Auth0
AUTH0_AUDIENCE=mern-order-app-api
AUTH0_ISSURE_BASE_URL=https://dev-sbpc2bue8v6q77b8.us.auth0.com/

# Cloudinary
CLOUDINARY_CLOUD_NAME= ... // Secret :)
CLOUDINARY_API_KEY= ... // Secret :)
CLOUDINARY_API_SECRET= ... // Secret :)

# Stripe 
FRONTEND_URL=http://localhost:5173
STRIPE_API_KEY= ... // Secret :)
STRIPE_WEBHOOK_SECRET= ... // Secret :)
```

Start the app

```bash
  npm run dev
```

NOTE: Run Frontend also.




## How To Use

Project Deploy on <a href="https://render.com/" target="_blank">Render</a> platform,
You can use the project through the following link:
<a href="https://mern-order-app-frontend.onrender.com">Link</a>



## Credits

This software uses the following open source packages:

- [Node.js](https://nodejs.org/)
- [Express.js](https://expressjs.com/)
- [MongoDB](https://www.mongodb.com/)
- [Mongoose](https://mongoosejs.com/)
- [Nodemon](https://www.npmjs.com/package/nodemon)
- [JsonWebToken](https://jwt.io/)
- [Multer](https://www.npmjs.com/package/multer)
- [dotenv](https://www.npmjs.com/package/dotenv)
- [Cloudinary](https://console.cloudinary.com)
- [Stripe](https://dashboard.stripe.com)
- [Auth0](https://auth0.com/)



## License

Chris Blakely [Chris Blakely](https://www.youtube.com/@ChrisBlakely)

---

> Linkedin [Amir Battal](https://www.linkedin.com/in/amir-battal/) &nbsp;&middot;&nbsp;
> GitHub [@Amir-Battal](https://github.com/Amir-Battal) &nbsp;&middot;&nbsp;
