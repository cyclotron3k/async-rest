# Async::REST

An asynchronous client and server implementation of RESTful interfaces.

[![Build Status](https://secure.travis-ci.org/socketry/async-rest.svg)](http://travis-ci.org/socketry/async-rest)
[![Code Climate](https://codeclimate.com/github/socketry/async-rest.svg)](https://codeclimate.com/github/socketry/async-rest)
[![Coverage Status](https://coveralls.io/repos/socketry/async-rest/badge.svg)](https://coveralls.io/r/socketry/async-rest)

[async]: https://github.com/socketry/async
[async-io]: https://github.com/socketry/async-io
[falcon]: https://github.com/socketry/falcon

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'async-rest'
```

And then execute:

	$ bundle

Or install it yourself as:

	$ gem install async-rest

## Usage

### GET a remote resource

```ruby
require 'async'
require 'async/rest/resource'

API_URL = "https://reqres.in/api"

Async.run do
	api = Async::REST::Resource.for(API_URL)
	
	response = api.with(path: "users").get(page: 2)
	
	pp response.read
	
	api.close
end
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

Released under the MIT license.

Copyright, 2015, by [Samuel G. D. Williams](http://www.codeotaku.com/samuel-williams).

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
