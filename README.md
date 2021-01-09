# ruby-notes

## objects
`object.methods()` - Ruby objects are happy to tell you what methods they provide. You simply call the methods method on them  

## strings
`"The number #{a} is less than #{b}"` - example of string interpolation (a and b are variables that will get evaluated concatenated with rest of the string)
`string literal created with single quote does not support interpolation` - important difference between single and double quoted string literals  
`"[Luke:] I can’t believe it. [Yoda:] That is why you fail.".include?('Yoda')` - check if string includes Yoda string  
`"Ruby is a beautiful language".start_with?("Ruby")` - checks whether string starts with Ruby  
`"I can't work with any other language but Ruby".end_with?("Ruby")` - checks whether string ends with Ruby  
`"I am a Rubyist".index("R")` - looks for string index  
`'This is Mixed CASE'.downcase()` - lowercase  
`'This is Mixed CASE'.upcase()` - uppercase  
`"I should look into your problem when I get time".gsub('I','We')` - globbaly replace all occurances of the substring in the string  

## boolean
```
def check_sign(number)
  if number > 0
    "#{number} is positive"
  elsif number == 0
    "0"
  else
    "#{number} is negative"
  end        
end
```
example of method that uses conditionals  
`objects false and nil equates to false. Every other object like say 1, 0, "" are all evaluated to be true.` - truthiness in ruby  

## loops
```
loop do
  unless !monk.nirvana?
      break
  end 
  monk.meditate
end
```
something like while loop. it stops when there is break statement  

```
def ring(bell, n)
  n.times do
    bell.ring
  end
end
```
for loop example in method in ruby  

## arrays  
`[1, 2, 3, 4, 5][-1]` - Array indexes can also start from the end of the array, rather than the beginning! In Ruby, this is achieved by using negative numbers. This is called reverse index lookup.  
`[1, 2, 3, 4, 5].push("woot")` - push additional item to arrray  
`[1, 2, 3, 4, 5].map { |i| i + 1 }` - resulting array [2, 3, 4, 5, 6]  
`[1,2,3,4,5,6].select {|number| number % 2 == 0}` - array filtering  
`[1,3,5,4,6,7].delete(5)` - result [1,3,4,6,7]  
`[1,2,3,4,5,6,7].delete_if{|i| i < 4 }` - removes all numbers smaller than 4  
```
def array_copy(source)
  destination = []
  for i in source
    if i < 4 
      destination.push(i)
    end
  end
  return destination
end
```
method that copies one array into another  
```
def array_copy(source)
  destination = []
  source.each do |i|
    if i < 4
      destination.push(i)
    end
  end
  return destination
end
```
method that copies one array into another

## hashes, maps, dictionaries
```
restaurant_menu = {
  "Ramen" => 3,
  "Dal Makhani" => 4,
  "Tea" => 2
}
``` 
one way of defining hash  
`restaurant_menu["Ramen"]` - accessing key  
```
restaurant_menu = {}
restaurant_menu["Dal Makhani"] = 4.5
restaurant_menu["Tea"] = 2
```
modyfing key values in the hash  
```
restaurant_menu = { "Ramen" => 3, "Dal Makhani" => 4, "Coffee" => 2 }
restaurant_menu.each do |key, val|
  restaurant_menu[key] = val*0.1+val
end
```
iterating over hash  
```
def artax
  a = [:punch, 0]
  b = [:kick, 72]
  c = [:stops_bullets_with_hands, false]
  key_value_pairs = [a,b,c]
  Hash[key_value_pairs]
end
p artax
```
hash definition

## classes, objects
`puts 1.is_a?(Integer)` - checks whether objects is of a given class  
`Object.new()` - create new instance of a class  
```
class Rectangle
  def initialize(length, breadth)
    @length = length
    @breadth = breadth
  end

  def perimeter
    2 * (@length + @breadth)
  end
  
  def area 
    @length*@breadth
  end
end
```
class definition
