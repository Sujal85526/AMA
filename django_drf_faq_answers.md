# Django & DRF Q&A 

---

## 1. What is the difference between a Django project and a Django app? 🔧

- **Project**: The top-level configuration for a website; contains global settings, URL configuration, WSGI/ASGI entrypoints, and one or more apps.
- **App**: A reusable, self-contained module that provides specific functionality (e.g., blog, auth). Apps live inside a project and are added to `INSTALLED_APPS`.

Example: a project can contain `users`, `payments`, and `blog` apps.

---

## 2. What do `makemigrations` and `migrate` do in Django? ⚙️

- `python manage.py makemigrations` — inspects `models.py` changes and creates migration files describing schema changes.
- `python manage.py migrate` — applies pending migrations to the database (creates/updates tables, columns, constraints).

`makemigrations` = create migration files; `migrate` = execute them.

---

## 3. What is Django ORM and why is it used? 🧩

- **Django ORM** maps database tables to Python classes (models) and rows to objects. It provides a high-level API to query and manipulate the database using Python instead of raw SQL.
- **Why use it**: readability, productivity, database agnosticism, built-in protections (e.g., SQL injection mitigation), and integration with Django features.

---

## 4. What is a Serializer in Django REST Framework? 🔁

- A **Serializer** converts complex data types (model instances, querysets) to native Python datatypes suitable for rendering (JSON/XML) and vice versa.
- It also handles **validation** and deserialization when receiving input.

Example: `MyModelSerializer(serializers.ModelSerializer)` maps model fields to JSON fields and validates input.

---

## 5. What is the difference between `APIView` and `ModelViewSet` in DRF? 🔍

- **APIView**: Low-level class-based view for REST endpoints. You implement HTTP method handlers (`get`, `post`, `put`, `delete`) manually and have full control.
- **ModelViewSet**: High-level viewset that provides standard CRUD actions (`list`, `retrieve`, `create`, `update`, `destroy`) for a model automatically when given `queryset` and `serializer_class`. Works with routers to auto-generate routes.

Use `APIView` for custom behavior and `ModelViewSet` for standardized CRUD quickly.

---

## 6. What is the client–server architecture? 🖥️↔️📱

- A pattern where **clients** (browsers, mobile apps) make requests to **servers** that provide resources and services (APIs, web pages, data).
- Typically over HTTP(S). Servers host resources and handle business logic; clients initiate requests and render results.

---

## 7. What is the purpose of `fetch()` in JavaScript? 🌐

- `fetch()` is a browser API for making HTTP requests. It returns a Promise and is commonly used to request JSON or other resources from APIs.

Example: `const res = await fetch('/api/items'); const data = await res.json();`

---

## 8. Explain Django architecture (MTV) 🏗️

- **M**odel: Data layer (ORM + models) — defines data structure and DB interaction.
- **T**emplate: Presentation layer — HTML generation and templating.
- **V**iew: Business logic — receives requests, interacts with models, returns responses or renders templates.

Other components: URL dispatcher, middleware, forms, authentication, admin, settings, WSGI/ASGI.

---

## 9. Explain URL routing in Django 🧭

- Django maps incoming URL paths to view callables via `urlpatterns` in `urls.py` using `path()` or `re_path()`.
- You can include app-specific `urls.py` from the project-level `urls.py` for modular routing.
- Named routes allow reverse URL lookup with `reverse()` or the `{% url %}` template tag.

Example: `path('articles/<int:id>/', views.detail, name='article-detail')` maps to `views.detail(request, id)`.

---

## 10. What is the purpose of `manage.py`? 🛠️

- `manage.py` is a command-line utility that wraps `django-admin` with your project's settings. It runs tasks such as starting the dev server, running migrations, opening a shell, creating apps, and running tests.

Common commands: `runserver`, `migrate`, `makemigrations`, `createsuperuser`, `shell`.

---

## 11. Difference between aggregations and annotations in Django ORM 📊

- **Aggregation** (`.aggregate()`): computes values over an entire queryset (e.g., `Sum`, `Avg`, `Count`) and returns a single dictionary with aggregate values. Example: `Order.objects.aggregate(total=Sum('amount'))` → `{'total': 12345}`.
- **Annotation** (`.annotate()`): computes values per object and attaches them as extra fields on each queryset item. Example: `Customer.objects.annotate(order_count=Count('orders'))` adds an `order_count` attribute to each `Customer` instance.


---
