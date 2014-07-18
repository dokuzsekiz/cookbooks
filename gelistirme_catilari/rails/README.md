# Rails

## Debug

### Logger

Debug with `logger.(debug|info|warn|error|fatal)`

```ruby
logger.debug "Person attributes hash: #{@person.attributes.inspect}"
logger.info "Processing the request..."
logger.fatal "Terminating application, raised unrecoverable error!!!"
```

## Migrations

### Reset column information

`ModelName.reset_column_information`

### Add column

`generate migration AddIpToTransactions ip:string` will generate


```ruby
class AddIpToTransactions < ActiveRecord::Migration
  def change
    add_column :transactions, :ip, :string
  end
end
```

### Data Types

* :binary
* :boolean
* :date
* :datetime
* :decimal
* :float
* :integer
* :primary_key
* :references
* :string
* :text
* :time
* :timestamp

**Only PG**
* :cidr_address
* :ip_address
* :mac_address
* :hstore
* :array

**Example**

```ruby
create_table :network_types do |t|
  t.cidr :cidr_address
  t.inet :ip_address
  t.macaddr :mac_address
end
```

## Code Quality

### Rails Best Practise

* [Rails best practise](https://github.com/railsbp/rails_best_practices) is a code metric tool to check the quality of rails codes.
* Add `gem 'rails_best_practices'` to Gemfile
* Generate `rails_best_practices.yml` file with `rails_best_practices -g`
* At the root directory of rails app `rails_best_practices .` or html output `rails_best_practices -f html .`

## Working with time zones

DO

```ruby
2.hours.ago # => Fri, 02 Mar 2012 20:04:47 JST +09:00
1.day.from_now # => Fri, 03 Mar 2012 22:04:47 JST +09:00
Date.today.to_time_in_current_zone # => Fri, 02 Mar 2012 22:04:47 JST +09:00
Date.current # => Fri, 02 Mar
Time.zone.parse("2012-03-02 16:05:37") # => Fri, 02 Mar 2012 16:05:37 JST +09:00
Time.zone.now # => Fri, 02 Mar 2012 22:04:47 JST +09:00
Time.current # Same thing but shorter. (Thank you Lukas Sarnacki pointing this out.)
Time.zone.today # If you really can't have a Time or DateTime for some reason
Time.zone.now.utc.iso8601 # When supliyng an API (you can actually skip .zone here, but I find it better to always use it, than miss it when it's needed)
Time.strptime(time_string, '%Y-%m-%dT%H:%M:%S%z').in_time_zone(Time.zone) # If you can't use Time#parse
```

DO NOT

```ruby
Time.now # => Returns system time and ignores your configured time zone.
Time.parse("2012-03-02 16:05:37") # => Will assume time string given is in the system's time zone.
Time.strptime(time_string, '%Y-%m-%dT%H:%M:%S%z') # Same problem as with Time#parse.
Date.today # This could be yesterday or tomorrow depending on the machine's time zone.
Date.today.to_time # => # Still not the configured time zone.
```
