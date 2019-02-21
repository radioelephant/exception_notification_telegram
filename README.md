# ExceptionNotificationTelegram

Welcome to your new gem! In this directory, you'll find the files you need to be able to package up your Ruby library into a gem. Put your Ruby code in the file `lib/exception_notification_telegram`. To experiment with that code, run `bin/console` for an interactive prompt.

TODO: Delete this and the text above, and describe your gem

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'exception_notification_telegram'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install exception_notification_telegram

## Usage
In order to receive exceptions in Telegram, you need to create a [Telegram Channel](https://telegram.org/tour/channels) and a [Telegram Bot](https://core.telegram.org/bots). Then, add the bot to the channel from the Telegram app.

To configure it, you need to set the channel name and the bot token, like this:

```ruby
Rails.application.config.middleware.use ExceptionNotification::Rack,
                                        email: {
                                          email_prefix: '[PREFIX] ',
                                          sender_address: %{"notifier" <notifier@example.com>},
                                          exception_recipients: %w{exceptions@example.com}
                                        },
                                        telegram: {
					  token: 'TELEGRAM-TOKEN',
                                          channel: '@channel_name'
                                        }
```


## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/github_username/exception_notification_telegram. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the ExceptionNotificationTelegram project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/github_username/exception_notification_telegram/blob/master/CODE_OF_CONDUCT.md).
