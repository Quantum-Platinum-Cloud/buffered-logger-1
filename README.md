# buffered-logger

buffered-logger is a concurrency safe logger. It buffers each logging statement and writes to the log file all at once.

## Description

buffered-logger is designed to be used in multithreaded rack servers and includes a middleware to automatically capture and
write the buffered log statements during each request.

## Installation

If you're using rails, add this line your application's Gemfile:

    gem "buffered-logger", require: "buffered_logger/rails"

Otherwise add this line to your application's Gemfile:

    gem "buffered-logger"

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install buffered-logger

## Usage

```ruby
require "buffered_logger"

MyApp.logger = BufferedLogger.new("myapp.log")

use BufferedLogger::Middleware, logger
run MyApp
```

## Contributing

Fork, branch & pull request.
