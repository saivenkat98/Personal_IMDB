# 🎬 Personal IMDB – A Full-Stack Movie Review Platform

**Personal IMDB** is a full-stack application where users can explore movies, watch trailers, and post their own reviews — all powered by a robust backend and a dynamic frontend.

This project was designed as a hands-on exploration into **NoSQL data modeling**, **RESTful API design**, and **real-time user interaction**. It blends the flexibility of **MongoDB**, the power of **Spring Boot**, and the interactivity of **React** — wrapped in a responsive UI styled with **Bootstrap**.

---

## 🛠️ Backend – Spring Boot + MongoDB

The backend is a scalable REST API developed using **Spring Boot**, backed by **MongoDB** for flexible, document-oriented storage. The design follows a **layered architecture**, separating concerns across controllers, services, and repositories.

### 📂 Data Modeling with MongoDB

- Movies and reviews are stored as **JSON-like documents** in MongoDB.
- Uses `ObjectId` as a unique identifier, allowing MongoDB to handle indexing and relationships efficiently.
- Unlike relational databases, there's no fixed schema — enabling flexible, evolving data models.

> This approach ensures that the platform can grow without tight coupling between entities.

### 🎞️ Movie APIs & Query Handling

- **MongoRepository** powers quick data access using built-in methods.
- Exposed REST endpoints to integrate backend to frontend.

> All queries are optimized via MongoDB indexing for fast lookups.

### ✍️ Review Management with MongoTemplate

- Reviews are stored in a separate collection and referenced in the `Movie` document using `@DocumentReference`.
- **MongoTemplate** enables atomic updates:
  - New reviews are *pushed* directly into a movie’s `reviewIds` array without replacing existing data.
  - Ensures consistent linkage between reviews and their parent movie.

> Dynamic updates mean reviews show up in real-time, with no downtime or data rewriting.

### ⚙️ Service & Controller Layers

- **Service layer** handles all business logic, keeping controllers clean and lightweight.
- **ReviewService** ensures atomic insertion of a review and simultaneous update to the associated movie.
- **@CrossOrigin** is enabled to allow secure communication from the frontend.

---

## ⚛️ Frontend – React + Bootstrap

The frontend delivers a clean, interactive user interface built with **React** and styled using **Bootstrap CSS**. It interacts directly with the Spring Boot API and updates the UI in real-time based on user activity.

### 🧩 Component Architecture & Routing

- Uses **React Router** to navigate across:
  - `/` → Movie carousel on the home page
  - `/Trailer/:ytTrailerId` → Play trailers using React Player
  - `/Reviews/:movieId` → View and submit reviews
- A global `Layout` component wraps all routes for consistent styling and navigation.

> Seamless client-side routing ensures a snappy single-page experience.

### 🔄 State Management & API Integration

- `useState` and `useEffect` manage local state and trigger backend fetches.
- **Axios** is configured with a base URL and handles all API calls:
  - Fetch all movies
  - Get movie details
  - Post new reviews

> Backend data updates instantly reflect in the UI without page reloads.

### 🎥 Movie Carousel & Trailer Integration

- The home page features a **carousel of movie posters**, built with `react-material-ui-carousel`.
- Clicking a movie leads to its trailer page, where **React Player** embeds the corresponding YouTube video.

> A highly visual interface makes exploring movies feel cinematic.

### 📝 Review System & Real-Time UI Updates

- Users can submit reviews via the `ReviewForm` component.
- On submission, reviews are posted to the backend and pushed to the movie’s review list.
- State updates automatically to reflect new reviews in the frontend UI.

> The experience feels instant — like commenting on a live feed.

### 🎨 Responsive UI with Bootstrap

- **Bootstrap** ensures that layouts are fluid and mobile-first.
- Components like Navbar, Cards, Buttons, and Forms use Bootstrap’s grid and utility classes.
- Minimal custom CSS keeps the focus on content and functionality.

---

## 🔗 Communication & Cross-Origin Support

- **CORS** is enabled on the backend using `@CrossOrigin`, allowing safe and secure integration with the frontend.
- Axios ensures smooth communication by handling base URL, headers, and responses uniformly.

---

## 🧪 Tech Stack Summary

| Layer        | Technology                   | Purpose                                   |
|--------------|-------------------------------|------------------------------------------|
| Backend      | Spring Boot, Java             | API, data logic, controller handling     |
| Database     | MongoDB, MongoRepository      | NoSQL storage and indexed queries        |
| DB Utility   | MongoTemplate                 | Atomic updates for embedded documents    |
| Frontend     | React, JavaScript             | UI, routing, component rendering         |
| Styling      | Bootstrap                     | Responsive layout and UI design          |
| Trailers     | React Player                  | YouTube video integration                |
| Carousel     | react-material-ui-carousel    | Movie carousel on home page              |
| API Handling | Axios                         | Frontend-backend communication           |

---

## 🚀 Future Improvements

- 🔐 User Authentication with JWT and secure review posting
- 🌟 Review rating system and upvotes
- 🗃️ Filters by genre, release year, or popularity
- 🌍 Global search functionality across movies

---

## 🎬 Final Take

**Personal IMDB** is more than just a movie listing app — it's an exercise in full-stack development, combining scalable backend architecture with a dynamic, user-friendly frontend. From atomic review updates to real-time UI changes, every layer is optimized for performance, clarity, and maintainability.

It’s the kind of project that not only *shows* what I can do — but how I think, build, and scale software.

---


<img width="1438" alt="1" src="https://github.com/user-attachments/assets/d0b09839-295e-4377-8b99-3c57b4d07936" />

<img width="1437" alt="2" src="https://github.com/user-attachments/assets/42e7f048-67d1-4d32-a083-e3b970ecb564" />

<img width="1440" alt="3" src="https://github.com/user-attachments/assets/e0c33d28-3676-4ebe-8671-9a37609168c7" />
