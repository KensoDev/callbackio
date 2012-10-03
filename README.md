# Callbackio

Better callbacks for your AR models

## Installation

Add this line to your application's Gemfile:

    gem 'callbackio'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install callbackio

## Usage

With Callbackio, callbacks are defined differently from what you may be used to.

The main method you should be working with is the `add_callback` method.

```ruby
add_callback :after :save :method_name
add_callback :before :update, :method_name
```

Callbackio will define the callback on the model, and will call the method you asked for.

## Why Callbackio

Callbackio has a few advantages to it over AR callbacks.

First, you can list all of the callbacks on a specific model with a simple call.

```ruby
User.registered_callbacks
```

This will list out all of the defined callbacks and the method those are going to call.

With Callbackio, you can also skip ALL of the callbacks.

```ruby
user = User.find(1)
user.first_name = "Avi"
user.last_name = "Tzurel"
user.skip_callbacks!
user.save
```

This will skip ALL of the callbacks defined with callback.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
