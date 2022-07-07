```
rails generate scaffold  User name photo bio:text posts_counter:integer
```

```
rails generate scaffold  Post title text:text comments_counter:integer likes_counter:integer
```

```
rails generate scaffold  Comment text:text 
```

```
rails generate scaffold Like
```

```
rails db:migrate
```


```
rails generate migration AddUserRefToPost user:references
```
```
add_reference :posts, :author, foreign_key: { to_table: :users }, null: false
```

```
rails g migration AddUserRefToComments user:references
```
```
add_reference :comments, :author, foreign_key: { to_table: :users }, null: false
```

```
rails g migration AddUserRefToLikes user:references
```
```
add_reference :likes, :author, foreign_key: { to_table: :users }, null: false
```

```
rails g migration AddPostRefToComments post:references
```

```
rails g migration AddPostRefToLikes post:references
```

```
rails db:migrate
```
