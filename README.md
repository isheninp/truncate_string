# smart string truncate with ... at the end

s = "Ruby on Rails, or Rails, is a server-side web application framework written in Ruby under the MIT License. Rails is a model–view–controller (MVC) framework, providing default structures for a database, a web service, and web pages."

limit = 100

p s[0..limit].split.reverse.drop(1).reverse.join(' ') + '...'

OR

 s[0..limit].rpartition(/[\s.,;]+/).first + '...'

 => "Ruby on Rails, or Rails, is a server-side web application framework written in Ruby under the MIT..."

```ruby
def smart_truncate(s, limit)
  s.length > limit ? s[0..limit].rpartition(/[\s.,;]+/).first + '...' : s
end
```
