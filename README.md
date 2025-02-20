# Project: Meal Ordering App

## Description

This project is a **Meal Ordering App** that allows users to browse available meals, add them to a cart, and place orders. The backend is built using **Node.js** with **Express**, while the frontend is developed using **React**. The app also features state management for the cart and user progress, with context-based solutions for handling the shopping cart and checkout functionality.

## Features

- View available meals.
- Add meals to the cart.
- Remove or adjust meal quantities in the cart.
- Checkout and place an order.
- JSON-based file storage for meals and orders (no database).

## Technologies

### Backend

- **Node.js**: Server environment.
- **Express.js**: Web framework for building APIs.
- **File System (fs/promises)**: Used to read/write data from/to JSON files.

### Frontend

- **React.js**: Library for building the UI.
- **Context API**: For managing global states like the cart and user progress.
- **Custom Hooks**: `useHttp` for handling API requests.



## Getting Started

### Prerequisites

- **Node.js**: Ensure you have Node.js installed (v14+).
- **npm or yarn**: Package manager to install dependencies.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-repository/meal-ordering-app.git
   ```

2. **Install dependencies:**
   - Navigate to the backend folder and run:
     ```bash
     cd backend
     npm install
     ```

   - Navigate to the frontend folder and run:
     ```bash
     cd frontend
     npm install
     ```

### Running the Backend

To run the Express server on `localhost:3000`:

```bash
cd backend
node server.js
```

This server will handle:
- **GET `/meals`**: Fetches available meals from `available-meals.json`.
- **POST `/orders`**: Places an order and appends it to `orders.json`.

### Running the Frontend

To start the React app on `localhost:3001`:

```bash
cd frontend
npm start
```

### Available Scripts

In the **frontend** directory, you can run:

- `npm start`: Starts the development server.
- `npm run build`: Builds the app for production.

## API Endpoints

- **GET `/meals`**: Fetches available meal options.
- **POST `/orders`**: Submits an order. Expects the following structure in the request body:
  ```json
  {
    "order": {
      "items": [
        { "id": "m1", "quantity": 2 },
        { "id": "m2", "quantity": 1 }
      ],
      "customer": {
        "email": "user@example.com",
        "name": "John Doe",
        "street": "123 Main St",
        "postal-code": "12345",
        "city": "Sample City"
      }
    }
  }
  ```

## State Management

- **CartContext**: Manages the items in the user's cart (add, remove, clear).
- **UserProgressContext**: Tracks user progress (cart or checkout phase).

## Custom Hook: `useHttp`

The `useHttp` custom hook handles all HTTP requests. It simplifies data fetching and error handling.

```js
const { data, isLoading, error, sendRequest, clearData } = useHttp(
  'url', 
  config, 
  initialData
);
```



