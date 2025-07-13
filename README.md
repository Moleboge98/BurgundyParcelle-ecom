# Burgundy Parcelle - A Modern E-Commerce Marketplace

Burgundy Parcelle is a full-featured e-commerce platform built with Django. It's designed to function as a multi-vendor marketplace, allowing different sellers to create their own stores and list products, while buyers can browse, purchase, and review items from across the platform.



# Features

Dual User Roles: A clear distinction between Buyers and Vendors, each with their own capabilities and dashboard views.



Vendor Storefronts: Vendors can create and manage their own unique store within the marketplace.



Product Management: Vendors have full control to add, edit, and delete products from their dashboard.



Product Categories: Products are organized into categories, which can be managed through the Django admin panel. Users can filter products by category on the homepage.



Shopping Cart: A fully functional shopping cart for buyers to add, view, and remove items.



Secure Checkout: A checkout process that creates a formal order, adjusts product stock, and sends an invoice to the user's console.



Product Reviews: Buyers can leave a rating and a text review on products they have purchased.



Password Reset: A complete, email-based password reset flow for all users.



Custom Admin Panel: A robust Django admin interface for site administrators to manage users, stores, products, and categories.



# Tech Stack

Backend: Python with the Django Framework



Database: MongoDB



Database Connector: djongo



Frontend: HTML with Tailwind CSS for styling



# Setup and Installation

Follow these steps to get the project running on your local machine.



1. Prerequisites

Python 3.x



MongoDB installed and running on its default port (27017).



pip for package management.



2. Clone the Repository

Clone this project to your local machine.

```

git clone <your-repository-url>

cd <your-project-directory>

```

3. Set Up a Virtual Environment

It is highly recommended to use a virtual environment to manage project dependencies.



# Create a virtual environment
```

python -m venv venv

```

# Activate the virtual environment

# On macOS/Linux:
```
source venv/bin/activate
```
# On Windows:
```
venv\Scripts\activate


```
4. Install Dependencies

First, create a requirements.txt file to lock your project's dependencies.

```

pip freeze > requirements.txt



Then, install all the necessary packages from this file.



pip install -r requirements.txt

```

This will install Django, djongo, and any other packages your project needs.



5. Configure Database Settings

Open the eCommerce_app/settings.py file and ensure your DATABASES configuration is set up for MongoDB.



# In eCommerce_app/settings.py



DATABASES = {

    'default': {

        'ENGINE': 'djongo',

        'NAME': 'burgundy_parcelle_db', # Or your preferred database name

        'ENFORCE_SCHEMA': False,

        'CLIENT': {

            'host': 'mongodb://localhost:27017/'

        }

    }

}



6. Configure Email and Login URL

Add the following lines to the bottom of your eCommerce_app/settings.py file to handle email output and login redirects.



# In eCommerce_app/settings.py



# For development, print emails to the console instead of sending them

EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'



# Tell Django where your custom login page is

LOGIN_URL = 'shop:login'



7. Run Database Migrations

Apply the database schema to your new MongoDB database.

```

python manage.py makemigrations

python manage.py migrate

```

8. Create a Superuser

Create an administrator account to access the Django admin panel.

```

python manage.py createsuperuser

```

Follow the prompts to set your username, email, and password.



9. Run the Development Server

You're all set! Start the server.

```

python manage.py runserver

```

The application will be available at https://www.google.com/search?q=http://127.0.0.1:8000/.



Usage

Create Categories: Log into the Django admin at /admin/ with your superuser account. Navigate to the "Categories" section and add a few product categories (e.g., Fashion, Electronics, Books).



Register Users: Register a new user as a "Vendor" and another as a "Buyer".



Create a Store: Log in as the vendor and create a store from the vendor dashboard.



Add Products: Add a few products to the store, assigning them to the categories you created.



Shop: Log in as the buyer, browse products, filter by category, add items to your cart, and complete the checkout process.
