---
tags: readme
language: ruby
resources: 0
track: web development
topic: ruby
unit: hashes
lesson: overview, creation, manipulation, retrieval
---

# Hashesasdf

## Introduction
* "Hashes are a lot like arrays: they have a bunch of slots that can point to various objects. However, in an array, the slots are lined up in a row, and each one is numbered (starting from zero). In a hash, the slots aren’t in a row (they are just sort of jumbled together) and you can use any object to refer to a slot, not just a number." - From [Chris Pine's Learn to Program, page 108](http://books.flatironschool.com/books/43?page=108)

## Structure
* Hashes are structured with keys and values.

```ruby
hash = {:key => "value", :another_key => "another value"}
```

## Creation
* Making a new hash can be accomplished in a couple different ways.

```ruby
my_hash = Hash.new
#  └── {}
my_hash = {}
#  └── {}
```
* Initializing a hash that already contains data is a lot like initiating an array with data.

```ruby
positions = {:office_manager => "Carley", :coo => "Kristi", :placements => "Jackie"}
#  └── {:office_manager=>"Carley", :coo=>"Kristi", :placements=>"Jackie"}
```

## Retrieval
* Retrieving data is similar to retrieving data from an array but instead of giving the index number in brackets, you give the name of the key.

```ruby
positions = {:office_manager => "Carley", :coo => "Kristi", :placements => "Jackie"}
puts positions[:office_manager]
#  └── Carley
```

## Manipulation
* Instead of  `<<` shovel method, hashes use an `[:key]=` method to add data. Say we want to add the key of `:content` and have it point to value of `"Stephanie"`. We would simply write the second line of code below:

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
