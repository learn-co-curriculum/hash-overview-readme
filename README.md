# Hashes

1. intro: what? why?
2. creation
3. accessing
4. adding
5. coming up: manipulating and iterating

Then, repl to 1. create, 2. access, 3. add 

Next reading: manipulating and iterating over hashes readme and repl to get familiar with iteration, using some helpful hash methods and reading docs on hashes. Then, key for min value lab

Next reading: building nested hashes + repl . Then, simple nesting lab (re-do b/c coding in spec file 

## Introduction
> Hashes are a lot like arrays: they have a bunch of slots that can point to various objects. However, in an array, the slots are lined up in a row, and each one is numbered (starting from zero). In a hash, the slots aren’t in a row (they are just sort of jumbled together) and you can use any object to refer to a slot, not just a number. 
> 
> –– [Chris Pine's Learn to Program, page 108](http://books.flatironschool.com/books/43?page=108)


Up until this point, we've stored our data in list-form using arrays. Let's take a look at an example where an array would not be sufficient to meet our storage needs.

## Example: Customs Inspector

![Herman Melville](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/Herman_Melville.jpg/160px-Herman_Melville.jpg)

The year is 1866 and we work beside [Herman Melville](https://en.wikipedia.org/wiki/Herman_Melville) (author of Moby Dick) as a customs inspector in New York. (I know, when did our lives become so old-timey and exciting? FYI he really did work there in 1866.) We're in charge of inspecting an incoming shipment and we need to track the items we're inspecting by listing each type of item (for example whale bone corset, porcelain, oil painting, other old fashioned item, etc) and the number of that item in the shipment. 

Let's say our shipment containts 5 whale bone corsets, 2 porcelain vases and 3 oil paintings. If we tried to store them in an array in list form, it would look like this: 

```ruby
old_fashioned_things = ["whale bone corset", "porcelain vase", "oil painting"
```
As it stands, there is no way for us to include the count of each item in a way that associates the item to it's count. That's no good. How is our co-worker Herman Melville going to be able to tell how many of each item are in this shipment? 

Here's where a hash can come in handy. With a hash, we can store a list of associated pairs. In other words, we can store the pairs of item/count. Let's take a look: 

```ruby
old_fashioned_things = {
  "whale bone corset" => 5, 
  "porcelain vase" => 2, 
  "oil painting" => 3
}
```

## Structure
Hashes are structured with keys and values. Each key/value pair makes up one unit in the hash. The entire collection of key/value pairs, which are comma separated, is enclosed in curly braces, `{ }`. 

```ruby
hash = {:key => "value", :another_key => "another value"}
```

You can think of a hash as a dictionary. The key is the reference point that is set equal to an associated value. In fact, a dictionary makes a pretty good hash example. Let's take a look: 

```ruby
dictionary = {

  "apple" => "a delicious fruit", 
  "this readme" => "wonderful and informative piece of reading", 
  "Moby Dick" => "a novel by my good friend, Herman Melville"
  
}
```
Keys in hashes can be strings, symbols or integers. They are set equal to their associated values via the hash-rocket, `=>`.  

## Creating Hashes

We can make a new hash via the class constructor or the literal constructor, just like arrays. 

### The Class Constructor

```ruby
my_hash = Hash.new
  => {}  
```

### The Literal Constructor

```ruby
my_hash = {}
  => {}
```

Initializing a hash that already contains data is a lot like initiating an array with data. We use the literal constructor:

```ruby
pets = {:cat => "Maru", :dog => "Pluto"}
  => {:cat => "Maru", :dog => "Pluto"}
```
Let's practice by making some hashes below: 


%%% 

## Constructing Hashes

Use the literal constructor to set the variable, `my_hash`, equal to a hash with key/value pairs of your choice. Remember, key/values pairs are associative. It doesn't make sense to have a key/value pair of `"my_name" => 78`. It *does* make sense to have a key/value pair of `"my_name" => "Herman Melville"` (if you happen to be that author, of course). 

```ruby
my_hash = { <delete this and fill out your own key/value pairs!> }

~~~solution

my_hash = {"my_name" => "Herman Melville", "my_novel" => "Moby Dick}

~~~validation 

assert.StrictEqual(response, 

```
## Retrieval
* Retrieving data is similar to retrieving data from an array but instead of giving the index number in brackets, you give the name of the key.

```ruby
positions = {:office_manager => "Carley", :coo => "Kristi", :placements => "Jackie"}
puts positions[:office_manager]
#  └── Carley
```

## Manipulation
* Instead of  `<<` shovel method, hashes use an `[:key]=` method to add data. Say we want to add the key of :content and have it point to value of "Stephanie". We would simply write the second line of code below:

```ruby
positions = {:office_manager => "Carley", :coo => "Kristi", :placements => "Jackie"}
positions[:content] = "Stephanie"
puts positions.inspect
#  └── {:office_manager=>"Carley", :coo=>"Kristi", :placements=>"Jackie", :content=>"Stephanie"}
```
* To add data, you call the name of the hash, followed by a beginning bracket, followed by the name of the new key, followed by a closing bracket, followed by an equals sign, followed by the name of the new value.

## Example
* Just like arrays, hashes can contain integers, strings, arrays, hashes, and more. Here's an example using Flatiron School:

```ruby
{
  :students => ["Brandon", "Simon", "Vanessa", "Carl"], 
  :teachers => ["Arel", "Avi", "Logan", "Amanda"], 
  :locations => ["Brooklyn", "Manhattan"]
}
```
