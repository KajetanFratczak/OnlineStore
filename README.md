# Documentation

## Project Topic: Online Store

---

### Project Setup
The project is built using **React** and **Node.js with Express**.

#### Frontend
- React
- React DOM
- React Router DOM
- Context API (state management)
- Axios (API communication)

#### Backend
- Express.js
- Mongoose
- MongoDB
- JSON Web Token (JWT)
- User Authorization Middleware
- CORS
- Body Parser

---

### How to Run

#### Backend

1. **Install Dependencies:**
   Run the following command in the root directory:
   ```bash
   npm install
   ```

2. **Start the Server:**
   You can start the server from the root directory using:
   ```bash
   npm start
   ```
   Or navigate to the `server/` directory and run:
   ```bash
   node server.js
   ```

   The server will run on `http://localhost:8080`.

   **Note:** Ensure you have MongoDB running locally or update `server/.env` with your MongoDB URI.

#### Frontend

1. **Navigate to the Frontend Directory:**
   ```bash
   cd sklep_internetowy
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Start the Development Server:**
   ```bash
   npm run dev
   ```

   The frontend will be available at the URL provided by Vite (typically `http://localhost:5173`).

---

### Project Structure

#### Backend

- **`server/`**:
  - **`config/`**:
    - `database.js`: Connects the application to the MongoDB database using Mongoose.
    - `seedDatabase.js`: Populates the MongoDB database with sample data.

  - **`middleware/`**:
    - `auth.js`: User authorization and role verification.

  - **`models/`**:
    - Mongoose schemas for collections: `Order`, `Product`, `Review`, `User`.

  - **`routes/`**:
    - Express.js routes:
      - Order management.
      - Product management.
      - Review management.
      - User management.

  - `.env`: Environment variables definition.
  - `server.js`: Express.js server configuration.

#### Frontend

- **`public/`**:
  - `rotated_1.png`: Image used on the homepage.

- **`src/`**:
  - **`components/`**:
    - `Cart.jsx`: Cart management and order placement.
    - `Home.jsx`: Main page of the online store.
    - `Layout.jsx`: Page layout template.
    - `Login.jsx`: User login form.
    - `NoPage.jsx`: 404 error handling.
    - `OrderHistory.jsx`: User order history.
    - `ProductDetails.jsx`: Product details.
    - `ProductReview.jsx`: Product review management.
    - `Products.jsx`: Product list with search and filtering.
    - `Profile.jsx`: User profile details.
    - `Register.jsx`: New user registration.
    - `SingleProduct.jsx`: Single product display.

  - **`context/`**:
    - `AuthContext.jsx`: User authentication management.
    - `CartContext.jsx`: Shopping cart management.

  - **`mocks/`**:
    - `orders.js`: Sample order data.
    - `reviews.js`: Sample reviews.
    - `users.js`: Sample users.

  - **`utils/`**:
    - `api.js`: Functions for backend communication.

  - **Other files**:
    - `App.css`: Application styles.
    - `App.jsx`: Main application component.
    - `main.jsx`: React application entry point.
    - `ProtectedRoute.jsx`: Route protection in the application.

---

### Identified Issues and Proposed Improvements

1. **Issue**: Page does not automatically refresh after adding a review.
   **Solution**: Implement automatic component refresh.

2. **Feature**: Add logo and username after logging in.

3. **Feature**: Implement an administrator panel.

4. **Enhancement**: Migrate user, order, and review data from FakeStoreAPI to MongoDB and implement full CRUD operations.

---

### Current Implementation

- **Products**: Full integration with MongoDB.
- **Other Elements** (users, orders, reviews): Currently use FakeStoreAPI as the data source.

#### CRUD Operations

##### Products (MongoDB):
- **Create**: `POST /api/products`
- **Read**:
  - All products: `GET /api/products`
  - Product details: `GET /api/products/:id`

##### Users (FakeStoreAPI):
- **Register**: `POST /api/users/register`
- **Login**: `POST /api/users/login`

##### Orders (FakeStoreAPI):
- **Create**: `POST /api/orders`
- **Read User Orders**: `GET /api/orders/user/:user_id`

##### Reviews (FakeStoreAPI):
- **Add**: `POST /api/reviews`
- **Read Product Reviews**: `GET /api/reviews/:productId`
- **Delete Review**: `DELETE /api/reviews/:id`

---
