# Learning Ruby 💎

## 💽 Install

Download Ruby: https://www.ruby-lang.org/en/downloads/  
e.g. on Windows: https://rubyinstaller.org/downloads/  
Or use [TryRuby playground](https://try.ruby-lang.org/playground/)

## 👨‍🏫 Learn

- [TryRuby](https://try.ruby-lang.org/)
- [Learn Ruby in One Hour](https://youtu.be/f7-ezt0xlAI) by [TechmakerTV](https://www.youtube.com/channel/UCaT8uPGUYbdRsjm4cJy1D7w)

## 📃 Cheatsheet

- General

  - Parentheses: `puts "Hello"` is equivalent to `puts("Hello")`
  - Blocks:
    - `do ... end` (is equivalent to `{ ... }`)
    - `begin ...end`

- Flow Control

  - `if condition ... else ... end` e.g. `if my_string.empty? print "It's empty" end`
  - Ternary: `condition ? ... : ...`
  - `case variable when value; ... else ... end`  
    e.g. `case value when 1; puts "value is 1" when 2; puts "value is 2" else puts "value is neither 1 nor 2" end`
  - Loops:
    - `loop do ... break ... end`
    - `for ... in ... end` e.g. `for i in 1..3; puts i end`
    - `while/until condition ... end` e.g. `x = 0; while x <= 10; puts x; x += 1 end`
    - `begin ... end while/until condition`
  - More on Flow Control: [Introduction to Programming with Ruby: Flow Control](https://launchschool.com/books/ruby/read/flow_control) by [Launch School](https://launchschool.com/)

- Objects

  - `methods` array of methods for an object e.g. `1.methods`
  - `class` class of an object e.g. `1.class`

- Output

  - `"Hello World"`
  - `puts` (adds a new line) e.g. `puts "outputs a string"`, `puts 1 + 2`, `puts [12, 47, 35]`
  - `print` (no new line)
  - `<<` output to a file, append to an array e.g. `file << "some text"`

- `Number` class: `1.class`, `3.14.class`

  - Operators: `+` `*` `-` `/` `**`  
    Combine with `=` to assign to variable e.g. `x += 3`
  - `to_s` to string e.g. `40.to_s`
  - `times`: Enumerator from 0 to number e.g. `5.times { |i| print i }`

- `Boolean` class: `true.class`

  - Operators: `&&` `||`
  - Quick guide: [RubyGuides: Understanding Boolean Values in Ruby](https://www.rubyguides.com/2019/02/ruby-booleans/)

- `String` class: `"my string".class`

  - `length`
  - `reverse`
  - `*` to repeat e.g. `"Hi " * 5`
  - `to_i` to integer e.g. `"23 eggs".to_i`
  - `gsub` global substitute e.g. `"I love coding".gsub("coding", "eating")`
  - `lines` to split into an array of lines e.g. `"Hi\nHow are you?\n".lines`
  - `join` e.g. `"Hi\nHow are you?\n".lines.reverse.join`
  - `"#{variable}"` interpolate variable inside string e.g. `"Welcome #{username}!"`

- Symbols, similar to enums, e.g. `:blue`, `:red`, `:id`, `:name` (treated as strings)

- `Array` class: `[].class`

  - Example: `arr = [12, 47, 35]`
  - `min`, `max` e.g. `[12, 47, 35].min`
  - `sort` and `sort!` (see methods conventions section below)
  - `[n]` access the nth element e.g. `arr[0]`
  - `each` e.g. `arr.each { |value| puts value }`
  - `select` e.g. `arr.select { |value| value > 30 }`

- `Hash` class: `{}.class`

  - Example: `book_dates = {"Title 1": 1983, "Title 2": 2004}`
  - `new` e.g. `my_hash = Hash.new {0}` would use `0` as the default value for uninitialized keys
  - `[key]` e.g. `books["Awesome Book Title"]`
  - `keys` array of keys
  - `values` array of values
  - `each` e.g. `book_dates.each { |key, value| puts "#{key} written in #{value}" }`
  - `select` e.g. `book_dates.select { |key, value| value == 2004 }`

- Functions/Methods:

  - `def ... end` e.g. `def plus_one(value) value + 1 end`
  - Conventions:
    - `my_function!` (excalmation mark) indicates the function modifies the variable
    - `my_function?` (question mark) indicates the function returns a boolean
  - `return my_result`  
    (if no `return` specified, function returns the result of the last statement)
  - Parameters
    - Default value e.g. `def plus_one(value ` `= 0` `) value + 1 end`
    - `*` variadic function, arguments are in an array e.g. `def sum(*values) values.reduce(:+) end`  
      Calling `sum 2, 3, 4` returns `9`

- Classes:

  ```ruby
  class Book
    attr_accessor :content, :title, :author

      def initialize(title, author, content="")
        @title   = title
        @author  = author
        @content = content[0..39]
      end

      def to_s
        "#{title} by #{author}"
      end
  end

  my_book = Book.new "Awesome Title", "William S.", "Lorem ipsum..."
  puts my_book.content
  puts my_book.to_s
  ```
