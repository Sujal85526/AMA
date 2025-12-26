# Django & Django REST Framework — Quick FAQ

A concise set of answers to common Django and DRF questions. Each answer is short and practical for quick reference. 💡

---

### 1) What is the difference between a Django project and a Django app?

- **Project**: The overall configuration and settings for the entire site — contains `settings.py`, `urls.py`, and project-level configuration. 
- **App**: A self-contained component that provides specific functionality (e.g., blog, auth). A project can consist of many apps; apps are reusable across projects. 🔧

---

### 2) What do `makemigrations` and `migrate` do in Django?

- `python manage.py makemigrations` creates migration files that describe changes to models (it’s Django’s way of recording model schema changes). 
- `python manage.py migrate` applies those migration files to the database, executing the corresponding SQL (creating or altering tables). 

> Note: `makemigrations` is about generating migration files; `migrate` is about applying them to the DB.

---

### 3) What is Django ORM and why is it used?

- **Django ORM** is an object-relational mapper that lets you interact with the database using Python classes and methods instead of raw SQL. 
- It improves developer productivity, readability, portability between database backends, and helps avoid SQL injection issues by managing queries safely. 📦

---

### 4) What is a Serializer in Django REST Framework?

- A **Serializer** converts complex data types (e.g., Django model instances, querysets) to native Python datatypes for rendering into JSON/XML and also validates and converts incoming data back to model instances. 
- Think of it as the layer that handles data transformation and validation for API input/output. 🔁

---

### 5) What is the difference between `APIView` and `ModelViewSet` in DRF?

- **`APIView`**: Low-level class that gives full control over request handling; you define methods like `get`, `post`, `put`, `delete` manually. 
- **`ModelViewSet`**: High-level, provides default implementations for CRUD actions (`list`, `retrieve`, `create`, `update`, `destroy`) when used with serializers and queryset — great for standard model-backed APIs. Use `APIView` for custom behavior and `ModelViewSet` for fast, standard CRUD. ⚖️

---

### 6) What is the client–server architecture?

- A design pattern where **clients** (e.g., browsers, mobile apps) make requests to **servers** that provide services or resources (processing, storage, data). 
- The server handles requests, performs work (database access, business logic), and returns responses (HTML, JSON). This separation enables scalability and specialization. 🌐

---

### 7) What is the purpose of `fetch()` in JavaScript?

- `fetch()` is a modern web API for making network requests (HTTP) from the browser and receiving promises for responses. 
- It replaces older APIs like `XMLHttpRequest` for a simpler, Promise-based interface to perform GET/POST and handle JSON or other response types. 🔁

---

### 8) Explain Django architecture

- Django follows an **MTV** (Model-Template-View) pattern: 
  - **Model**: data layer (ORM models) that interacts with the database.
  - **Template**: presentation layer (HTML rendering).
  - **View**: controller-like layer that handles request logic and returns responses. 
- Additional layers: URL routing dispatches requests, middleware can inspect/modify requests/responses, and settings/config manage global behavior. 🏗️

---

### 9) Explain URL routing

- URL routing maps request URLs to view callables. In Django, you define `urlpatterns` in `urls.py` with `path()`/`re_path()` entries that connect URL patterns to view functions/classes. 
- It’s the first step in request handling — the router chooses which view should handle a given path and captures path parameters for the view to use. 

---

### 10) What is the purpose of `manage.py`?

- `manage.py` is a command-line utility that provides Django project management commands (running development server, migrations, shell, tests, custom commands). 
- It sets up the Django environment and points commands to your project’s settings module so you can perform administrative tasks easily. 🛠️

---

### 11) Difference between aggregations and annotations?

- **Aggregation**: computes a single summary value over a queryset (e.g., `Avg`, `Sum`, `Count`) and returns that result — typically using `aggregate()`. 
- **Annotation**: computes values per row and attaches those computed values to each queryset item (e.g., annotate each object with a computed `total`), using `annotate()`. 

---
