# virtus-matchers
RSpec matchers for Virtus

##Usage
A model like:
```ruby
class Foo
  include Virtus.model
  
  attribute :hello, String
  attribute :goodbye, String, default: 'Bye'
  attribute :name, String, strict: true
end
```

would have specs like:
```ruby
describe Foo do
  it { is_expected.to have_attribute(:hello, String) }
  it { is_expected.to have_attribute(:goodbye, String).with_default("Hello") }
  it { is_expected.to have_attribute(:name, String).strict }
end
