### Generate Class Scaffoldings
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
### Generate References among tables

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





To add data:
first_user = User.create(name: 'Tom', photo: 'https://unsplash.com/photos/F_-0BxGuVvo', bio: 'Teacher from Mexico.')
second_user = User.create(name: 'Lilly', photo: 'https://unsplash.com/photos/F_-0BxGuVvo', bio: 'Teacher from Poland.')

first_post = Post.create(user: first_user, title: 'Hello', text: 'This is my first post')
second_post = Post.create(user: first_user, title: 'Hello2', text: 'This is my second post')
third_post = Post.create(user: first_user, title: 'Hello3', text: 'This is my third post')
fourth_post = Post.create(user: first_user, title: 'Hello4', text: 'This is my fourth post')

comment01 = Comment.create(post: first_post, user: first_user, text: 'Hi Tom, This is Comment One!' )
comment02 = Comment.create(post: first_post, user: first_user, text: 'Hi Tom, This is Comment Two!' )
comment03 = Comment.create(post: first_post, user: first_user, text: 'Hi Tom, This is Comment Three!' )
comment04 = Comment.create(post: first_post, user: first_user, text: 'Hi Tom, This is Comment Four!' )
comment05 = Comment.create(post: first_post, user: first_user, text: 'Hi Tom, This is Comment Five!' )
comment06 = Comment.create(post: first_post, user: first_user, text: 'Hi Tom, This is Comment Six!' )
