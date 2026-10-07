---
apple-notes-id: BBA9D038-BFE5-4B95-8376-FE5AE1DF6B45
---
#ruby


```
[3] pry(main)> User.all.pluck(:id)
   (5.7ms)  SELECT "users"."id" FROM "users"
=> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17]
```



![[Pasted Graphic 1 18.png]]