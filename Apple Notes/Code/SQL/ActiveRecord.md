---
apple-notes-id: 010CFEFC-3B86-4830-B640-846FCA894CDA
---
### On the fly has-many-through

However, in addition to joining a direct association, ActiveRecord allows us to go even further and join indirect associations. This is almost like doing a has_many/through on the fly:


![[Pasted Graphic 11.png]]


which generates SQL like this:


![[Pasted Graphic 1 5.png]]



### Filtering with the where method

We can now filter the way we want to, with [ActiveRecord's where method](http://guides.rubyonrails.org/active_record_querying.html#specifying-conditions-on-the-joined-tables):


![[Pasted Graphic 2 4.png]]


which generates SQL like this:


![[Pasted Graphic 3 1.png]]


and retrieves data like this: 


![[Pasted Graphic 4 1.png]]



### Left join


```
Customer.left_outer_joins(:reviews).distinct.select('customers.*, COUNT(reviews.*) AS reviews_count').group('customers.id')
```

**Which produces:**


```
SELECT DISTINCT customers.*, COUNT(reviews.*) AS reviews_count FROM customers
LEFT OUTER JOIN reviews ON reviews.customer_id = customers.id GROUP BY customers.id
```