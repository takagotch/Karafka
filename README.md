### Karafka
---
https://github.com/karafka/karafka

```
gem 'karafka'
gem 'ruby-kafka', '~> 0.6.8'
git clone https://github.com/karafka/karafka-example-app ./example_app
cd ./example_app
bundle install

bundle exec karafka s
bundle exec rake waterdrop:send

```

```ruby
class App < Karafka::App
 setup do |config|
   config.client_id = 'my_application'
   config.backend = :inline
   config.batch_fetching = true
   config.batch_consuming = true
   config.kafka.seed_brokers = %w[kafka://127.0.0.1:9092]
 end
end

class App < Karafka::App
  after_init do |_config|
    Sedekiq::Logging.logger = Karafka::App.logger
  end
end

```

```
```
