Optimizations

1) Secure and Consistent Cart Data Handling

Files: cart/__init__.py and cart/dao.py
Issues:

Unsafe deserialization with eval().
Inconsistent serialization using str() instead of json.

Changes:

Replaced eval(contents) with json.loads(contents) for secure deserialization.
Used json.dumps(contents) instead of str(contents) to ensure consistent serialization.


2) Streamlining /browse Route

File: products/__init__.py
Issue:

Verbose iteration over database rows to construct Product objects.

Change:
Simplified the list_products() function using a list comprehension
