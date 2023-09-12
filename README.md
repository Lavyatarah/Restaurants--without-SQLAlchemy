# Restaurant Review System

 This Python program allows you to manage and analyze restaurant reviews from customers. In this system, you can create customers, restaurants, and add reviews, as well as perform various operations to access and analyze the data.

## Table of Contents
- [Getting Started](#getting-started)
- [Creating Instances](#creating-instances)
- [Adding Reviews](#adding-reviews)
- [Accessing Data](#accessing-data)
- [Calculating Average Star Rating](#calculating-average-star-rating)
- [Finding Customers](#finding-customers)
- [Finding Customers by Given Name](#finding-customers-by-given-name)

## Getting Started

Before using the Restaurant Review System, make sure you have the following Python files in your project directory:

- `Customer.py`: Contains the `Customer` class for managing customer data.
- `Review.py`: Contains the `Review` class for managing restaurant reviews.
- `Restaurant.py`: Contains the `Restaurant` class for managing restaurant data.

You can import these classes into your project by using the following statements:

```python
from Customer import Customer
from Review import Review
from Restaurant import Restaurant
```

## Creating Instances

You can create instances of customers and restaurants using the `Customer` and `Restaurant` classes. Here's how you can create instances:

```python
# Create instances
customer1 = Customer("George", "Washington")
customer2 = Customer("Uriah", "Smith")
restaurant1 = Restaurant("Ole Sereni")
restaurant2 = Restaurant("Hilton")
```

## Adding Reviews

You can add reviews to restaurants by specifying the customer and the rating. Ratings should be between 1 and 5. Here's how you can add reviews:

```python
# Adding reviews
customer1.add_review(restaurant1, 4)
customer2.add_review(restaurant1, 5)
customer2.add_review(restaurant2, 3)
```

## Accessing Data

You can access restaurant and customer data using various methods. For example, to access restaurant reviews and customer data, you can use the following code:

```python
# Accessing data
print("Reviews for", restaurant1.get_name())
for review in restaurant1.get_reviews():
    print("  Rating:", review.get_rating(), "by", review.get_customer().given_name)

print("Customers who reviewed", restaurant1.get_name())
for customer in restaurant1.get_customers():
    print("  Customer:", customer.given_name)
```

## Calculating Average Star Rating

You can calculate and print the average star rating for a restaurant using the `average_star_rating` method:

```python
# Calculate and print average star rating
print("Average star rating for", restaurant1.get_name(), ":", restaurant1.average_star_rating())
```

## Finding Customers

You can find a customer by their full name using the `find_by_name` method. If the customer is found, their full name will be displayed; otherwise, a message indicating that the customer was not found will be shown:

```python
# Find customer by name
found_customer = Customer.find_by_name("George", "Washington")
if found_customer:
    print("Found customer:", found_customer.full_name())
else:
    print("Customer not found.")
```

## Finding Customers by Given Name

You can find all customers with a given first name using the `find_all_by_given_name` method. This will return a list of matching customers:

```python
# Find all customers with a given name
customers_with_given_name = Customer.find_all_by_given_name("Uriah")
print("Customers with given name Uriah:")
for customer in customers_with_given_name:
    print("  Customer:", customer.full_name())
```

