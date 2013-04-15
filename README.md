# Abbyy

A Gem for using Abbyy’s Optical Character Recognition (OCR) SDK via their cloud API.

## Installation

Add this line to your application's Gemfile:

```ruby
  gem 'abbyy'
```

And then execute:

```sh
  $ bundle
```

Or install it yourself as:

```sh
  $ gem install abbyy
```

## Documentation

## Usage

### Authentication

When you register with Abbyy you will receive an Application ID and Application Password which you can use to authenticate requests to the web service.

```ruby
  Abbyy.configure do |c|
    c.application_id = "YOUR APPLICATION ID"
    c.application_password = "YOUR APPLICATION PASSWORD"
  end
```

### Processing an Image

```ruby
task = Abbyy.process_image('scanned_text.jpg')

until task.status == "Completed"
  sleep 1
  task = Abby.get_task_status(task.id)
end

file = Abby.download_result(task.result_url)
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
