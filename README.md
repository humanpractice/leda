# Leda

Rake and capistrano tasks for clone data between Rails application environments.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'leda'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install leda

## Usage

### 60 second version (not all working yet)

#### Define config/leda.rb

```
Leda.configure do |l|
  l.collection 'providers' do |c|
    c.postgresql tables: %w(practices offices practitioners)
  end
end
```

#### Dump data via rake or capistrano

```
$ bin/rake data:providers:dump
$ bin/cap production data:providers:dump
```

#### Restore data via rake

```
bin/rake data:providers:restore_from[production]
```

## Contributing

1. Fork it ( https://github.com/[my-github-username]/leda/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request