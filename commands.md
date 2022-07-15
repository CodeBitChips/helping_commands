### Generate Class Scaffoldings
```
rails generate model User name photo bio:text posts_counter:integer
```

```
rails generate model Post title text:text comments_counter:integer likes_counter:integer
```

```
rails generate model Comment text:text 
```

```
rails generate model Like
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

##### Add Users
```
first_user = User.create(name: 'Tom', photo: 'https://med.gov.bz/wp-content/uploads/2020/08/dummy-profile-pic-300x300.jpg', bio: 'Teacher from Mexico.')
```
```
second_user = User.create(name: 'Lilly', photo: 'https://www.kindpng.com/picc/m/252-2524695_dummy-profile-image-jpg-hd-png-download.png', bio: 'Teacher from Poland.')
```
##### Add Posts
```
first_post = Post.create(author_id: first_user.id, title: 'Hello', text: 'This is my first post')
```
```
second_post = Post.create(author_id: first_user.id, title: 'Hello2', text: 'This is my second post')
```
```
third_post = Post.create(author_id: first_user.id, title: 'Hello3', text: 'This is my third post')
```
```
fourth_post = Post.create(author_id: first_user.id, title: 'Hello4', text: 'This is my fourth post')
```
##### Add Comments
```
Comment.create(post_id: first_post.id, author_id: first_user.id, text: 'Hi Tom, This is Comment One!' )
```
```
Comment.create(post_id: first_post.id, author_id: first_user.id, text: 'Hi Tom, This is Comment Two!' )
```
```
Comment.create(post_id: first_post.id, author_id: first_user.id, text: 'Hi Tom, This is Comment Three!' )
```
```
Comment.create(post_id: first_post.id, author_id: first_user.id, text: 'Hi Tom, This is Comment Four!' )
```
```
Comment.create(post_id: first_post.id, author_id: first_user.id, text: 'Hi Tom, This is Comment Five!' )
```
```
Comment.create(post_id: first_post.id, author_id: first_user.id, text: 'Hi Tom, This is Comment Six!' )
```
