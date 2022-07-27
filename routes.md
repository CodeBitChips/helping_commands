In `routes.rb` file, provide index route.


```
root "welcome#index"
```
- root "welcome#index"
- root "controller#action"

In `welcome_controller.rb` file, put
```
class WelcomeController < ApplicationController
  def index
  end
end
```
In `views/welcome/index.html.erb` file, put
```
<h1>Index Page from Welcome Controller</h1>
```
