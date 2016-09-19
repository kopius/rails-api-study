# Rails as an API Study

Use your favorite search engine and the provided readings to research and answer
the following questions (no prior knowledge is expected).

In your answers, be sure to cite any relevant sources you consulted in your
search. We ask you to write answers in your own words in order to see how you
process what you've read. Please do not answer with direct quotes from source
material. Instead, digest what you've read and repeat it in your own voice.

Please note:

-   Many of the readings will mention the "view" layer. We won't be covering the
    view layer in this program.
-   We'll use our [rails-api-template](https://github.com/ga-wdi-boston/rails-api-template)
    repository as the basis for our rails applications.
    This template excludes the "view" layer.

## Required Readings

-   [Starting Ruby on Rails: What I Wish I Knew | BetterExplained](http://betterexplained.com/articles/starting-ruby-on-rails-what-i-wish-i-knew/)
-   [Intermediate Rails: Understanding Models, Views and Controllers | BetterExplained](http://betterexplained.com/articles/intermediate-rails-understanding-models-views-and-controllers/)
-   [Getting Started with Rails — Ruby on Rails Guides](http://guides.rubyonrails.org/getting_started.html)
-   [The Rails Command Line — Ruby on Rails Guides](http://guides.rubyonrails.org/command_line.html)
-   [Rails Routing from the Outside In — Ruby on Rails Guides](http://guides.rubyonrails.org/routing.html)
-   [Action Controller Overview — Ruby on Rails Guides](http://guides.rubyonrails.org/action_controller_overview.html)

## Define Model Responsiblities

In your own words, define what the responsibilities of the model layer are in
Rails.

```md

The model layer is where all the meaty logic lives in a Rails app. It gets
instructions from the controller. Based on those instructions, it talks to the
database and performs the necessary operations. If the controller passes it new
data to store, the model layer is responsible for validating that data before
storing it in the database. If the controller requests data to send back to the
client in a response, the model layer gets that data from the database and
performs any necessary processing before handing it to the controller to package
into a response. The model never talks directly to the client.

```

Sources:
-   [Starting Ruby on Rails: What I Wish I Knew | BetterExplained](http://betterexplained.com/articles/starting-ruby-on-rails-what-i-wish-i-knew/)
-   [Intermediate Rails: Understanding Models, Views and Controllers | BetterExplained](http://betterexplained.com/articles/intermediate-rails-understanding-models-views-and-controllers/)

## Define Controller Responsiblities

In your own words, define what the responsibilities of the controller layer are
in Rails.

```md

The controller layer takes the client request (properly routed by the router)
and calls methods in the model to do whatever needs to be done. The controller
doesn't do any heavy lifting; its job is to act as an intermediary between the
client and the model.

When a request is coming in, the controller parses it, performs any necessary
security operations to protect the app from invalid or malicious request, passes
any important incoming data to the model methods that need it, and stores any
data that might be needed later in a "session".

When a response is going out, the controller is responsible for taking data from
the model layer and packaging it in a response that the client will be able to
interpret.

```

Sources:
-   [Starting Ruby on Rails: What I Wish I Knew | BetterExplained](http://betterexplained.com/articles/starting-ruby-on-rails-what-i-wish-i-knew/)
-   [Intermediate Rails: Understanding Models, Views and Controllers | BetterExplained](http://betterexplained.com/articles/intermediate-rails-understanding-models-views-and-controllers/)
-   [Getting Started with Rails — Ruby on Rails Guides](http://guides.rubyonrails.org/getting_started.html)
-   [Action Controller Overview — Ruby on Rails Guides](http://guides.rubyonrails.org/action_controller_overview.html)

## Define Router Responsiblities

In your own words, define what the router does in Rails.

```md

The router is the first piece of Rails to see an incoming request from the
client. It looks at the request's URL and HTTP verb (GET, POST, PATCH, DELETE).
From that information (plus whatever constraints and special instructions we
have given it), the router passes the request along to the appropriate place in
the controller. It's like a switchboard that maps client requests to controller
actions.

```

Sources:
-   [Rails Routing from the Outside In — Ruby on Rails Guides](http://guides.rubyonrails.org/routing.html)

## The Request-Response Cycle in Rails

Starting with a client making a GET request to a particular URL, describe how
the parts of Rails interact to produce and send a response.

```md

The router receives a request from the client, looks at its HTTP verb and URL,
and matches the request to a controller action. In other words, it tells the
controller what the client wants to do.

The controller fires whichever action the router said to fire. This action will,
in turn, fire whatever methods in the model layer are necessary to generate the
correct response. The controller will parse any incoming data contained in the
request and pass it to the model methods that need it.

The model will do the heavy lifting. It interacts with the database, pulls out
any requested data (processing it if necessary), applies any other relevant
business logic, and sends data back to the controller.

The controller receives data from the model, packages it into a response, and
sends it back to the client.

```

Sources:
-   [Intermediate Rails: Understanding Models, Views and Controllers | BetterExplained](http://betterexplained.com/articles/intermediate-rails-understanding-models-views-and-controllers/)
-   [Getting Started with Rails — Ruby on Rails Guides](http://guides.rubyonrails.org/getting_started.html)
-   [Rails Routing from the Outside In — Ruby on Rails Guides](http://guides.rubyonrails.org/routing.html)
-   [Action Controller Overview — Ruby on Rails Guides](http://guides.rubyonrails.org/action_controller_overview.html)
