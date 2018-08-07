# Hashes

## Overview
We'll introduce a new data structure called hashes. We'll cover how to create them, retrieve data from, and add data to them.

## Objectives

1. Describe the structure of hashes and how they allow for data storage.
2. Create hashes using the literal constructor.
3. Retrieve data from hashes using the "bracket" method.
4. Add data to hashes using the "bracket-equals" method.


<iframe width="640" height="480" src="https://www.youtube.com/embed/0JSsFQGYaeA" frameborder="0" allowfullscreen></iframe>

### Why Hashes

> Hashes are a lot like arrays: they have a bunch of slots that can point to various objects. However, in an array, the slots are lined up in a row, and each one is numbered (starting from zero). In a hash, the slots aren’t in a row (they are just sort of jumbled together) and you can use any object to refer to a slot, not just a number.
>
> — [Chris Pine, *Learn to Program*, 2nd edition, pages 97-98](https://pine.fm/LearnToProgram/)


Up until this point, we've stored our data in list-form using arrays. An array is like a numbered list. It stores a group of items which are accessible via their location, or index number, in the list.

Imagine a grocery list: you need to go to the store and buy milk, eggs and bread. You could store your list like this:

```ruby
groceries = ["milk", "eggs", "bread"]
```

What happens when your list expands to include your other errands? Let's say you need to go the grocery store, the pharmacy, and the stationery store (you've been using up a lot of paper as you take copious notes on learning to code).

We could make one giant array that contains all of the items you need to buy:

```ruby
stuff_i_need = ["milk", "eggs", "bread", "toothpaste", "band-aids", "paper", "pens", "highlighter"]
```

This isn't very organized though. There is no way to distinguish the different categories of items.

This is where hashes come in. Hashes store data in an associated manner. With a hash, we can group our data into the necessary categories of "grocery", "pharmacy", and "stationery".

Hashes allow us to store named, or associated, data. Think of a dictionary or an address book. This allows us to store more complex collections of information than the arrays we've seen so far.

## Hash Structure and Usage

Hashes are structured with keys and values. Each key/value pair makes up one unit in the hash. The entire collection of key/value pairs, which are comma separated, is enclosed in curly braces `{ }`.

```ruby
hash = {"key" => "value", "another_key" => "another value"}
```

You can think of a hash as a dictionary. The key is the reference point that is set equal to an associated value. A vocabulary dictionary actually makes a pretty good example of the hash structure:

```ruby
dictionary = {

  "apple" => "a delicious fruit",
  "this readme" => "wonderful and informative piece of reading",
  "Moby Dick" => "a novel by my good friend, Herman Melville"

}
```

**//Flat-fact:** *In fact, "dictionary" is how the hash structure is known in some other programming languages such as Python and Objective-C.*

Keys in hashes can be any type of data: strings, integers or symbols (more on symbols later, don't worry about them for now). They are set equal to their associated values by using the `=>` symbol, known for this use as the "hash-rocket" (*because it looks like a little rocket shooting off towards the right*).  

### Example: Named Data

You can think of the data stored in a hash as being *associative*. In other words, keys point to data that is *related* to that key. Let's take a look at the following example:

```ruby
the_rock = {"name" => "Dwayne, The Rock, Johnson", "weight" => "a lot"}
```

If we tried to represent this same information as an array, it would look something like this:

```ruby
the_rock = ["name", "Dwayne, The Rock, Johnson", "weight", "a lot"]
```

Then, in order to access The Rock's name, we would have to use the following line of code:

```ruby
the_rock[1]
```

That requires us to remember, every time we want to access The Rock's name, that it is stored at the first index of `the_rock` array. That is too hard to keep track of.

In our `the_rock` hash, we have two key/value pairs. We have a key of `"name"`, which points to an associated value of The Rock's name. We have a key of `"weight"` which points to an associated value of The Rock's (real) weight. In this way, we are able to store data about The Rock in an organized and understandable manner.

#### Hash Keys and Uniqueness

A key in a hash can be a string, a symbol, or an integer as long as you only use each key once. This is because, unlike arrays, which store data in numbered indexes and access that data via the index numbers, hashes store data in keys and access that data by naming the key whose value we want to retrieve.

If you try to add a second key that duplicates an existing key, you will overwrite the value of the existing key, *instead of adding a new key/value pair*. Not only will duplicate hash keys simply not work as a way to store information, it just doesn't make sense.

Hashes are for storing named, or associative, data. Each key/value pair describes a unique attribute or unit of information. A person doesn't have two names, in reality. They might, though, have a name and a nickname. The data structure we are creating should mirror the real-world entity we are trying to describe. The uniqueness of our hash keys reflects that.

```ruby
the_rock = {"name" => "Dwayne Johnson", "stage_name" => "The Rock", "weight" => "a lot"}
```


### Example: Counting Data

![Herman Melville](http://flatiron-labs.s3.amazonaws.com/160px-Herman_Melville.jpg)

The year is 1866 and we work beside [Herman Melville](https://en.wikipedia.org/wiki/Herman_Melville) (author of Moby Dick) as a customs inspector in New York. (I know, when did our lives become so old-timey and exciting?) We're in charge of inspecting an incoming shipment and we need to track the items we're inspecting by listing each type of item (such as: whale bone corsets, porcelain vases, and oil paintings) along with the number of each kind of item in the shipment.

Let's say our shipment contains five (5) whale bone corsets, two (2) porcelain vases, and three (3) oil paintings. If we tried to store them in an array in list form, it would look like this:

```ruby
old_fashioned_things = [
  "whale bone corset",
  "whale bone corset",
  "whale bone corset",
  "whale bone corset",
  "whale bone corset",
  "porcelain vase",
  "porcelain vase",
  "oil painting",
  "oil painting",
  "oil painting"
]
```
As it stands, there is no way for us to include the count of each item in a way that associates the item to its count, so we have to store a separate occurrence of that item in order to track the shipment. Certainly for a small list this is manageable, but what happens when the shipment of Herman's first printing of *Moby Dick* arrives? We'd have to store 10,000 occurrences of the book instead of recording the count as value. That's no good!

So, how else can we help Herman keep track of how many of each item are included in the shipment? Here's where a hash can come in handy. With a hash, we can store a list of associated key/value pairs. In other words, we can store the pairs of item/count:

```ruby
old_fashioned_things = {
  "whale bone corset" => 5,
  "porcelain vase" => 2,
  "oil painting" => 3
}

first_printing = {
  "Moby Dick" => 10000
}
```
We'll be done recording these shipments in no time!

## Creating Hashes

We can make a new hash via the literal constructor, just like arrays.

### The Literal Constructor

```ruby
my_hash = {}
#=> {}
```

Initializing a hash that already contains data is a lot like initializing an array with data. We use the literal constructor:

```ruby
pets = {"cat" => "Maru", "dog" => "Pluto"}
#=> {"cat" => "Maru", "dog" => "Pluto"}
```
In the upcoming lab, you'll get a chance to practice making your own hashes.

**Note:** You may see something called the "class constructor", `Hash.new`, if you read outside sources on Hashes. Don't worry about this for now. We'll learn more about it later.

## Retrieving Data from Hashes

Retrieving data from a hash is similar to retrieving data from an array, but instead of giving an array the index number in brackets `[i]` we give a hash the name of the key `[key]`. If an array is a list in which we access index items by their number, a hash is a dictionary in which we access values by their key.

```ruby
pets = {"cat" => "Maru", "dog" => "Pluto"}

pets["cat"]
#=> "Maru"
```
Using `[]` is referred to as the **"bracket method".** It is actually a method just like any other––just like the methods you've been defining and like the methods available on objects such as Strings.

## Adding Keys and Values to Hashes

Adding items to hashes is easy. Instead of `<<` (the shovel method) that we use to add items to arrays, hashes use the **"bracket-equals"** method to add data. The full syntax for this takes the form of:

```ruby
person = {
  "name" => "Corinna",
  "age" => 36
}

# We can read Corinna's age with:
person["age"] #=> 36

# To add a key to the person hash:
person["hometown"] = "Massena, NY"
person["hometown"] #=> "Massena, NY"

# Let's add another key
person["favorite_thing"] = "Books"
person["favorite_thing"] #=> "Books"
```

The general syntax for adding a new value to a hash is: `hash["new_key"] = "New Value"`. `"new_key"` is the literal new key we added to the hash and we assigned the `"new_key"` a value of `"New Value"`.

Let's think about the distinction between the `<<` method for arrays and the `[]=`, or bracket-equals, method of adding data to hashes.

Hashes are *not numbered lists*. The data stored in them is not indexed by number, but instead associated to a unique key. Consequently a hash has no concept of the "end of the list", like an array. So the `<<` method, which tells the array to find the end of the list and add the new item to the next index, can't work on a hash.

While we were busy plugging away at our shipping manifest, Herman discovered an attempt to smuggle ten (10) jars of molasses past the inspection. Since molasses isn't illegal Herman decided not to confiscate it, but we do need to add it to the manifest so the merchant gets taxed on it. Accomplishing this with our hash would look like this:

```ruby
shipping_manifest = {
  "whale bone corset" => 5,
  "porcelain vase" => 2,
  "oil painting" => 3
}

shipping_manifest["jar of molasses"] = 10

puts shipping_manifest
# {
#   "whale bone corset" => 5,
#   "porcelain vase" => 2,
#   "oil painting" => 3,
#   "jar of molasses" => 10
# }
```

By the way, a hash that has counts of occurrences is a common data structure in programming, useful for generating charts and more. They are called [Histograms](https://en.wikipedia.org/wiki/Histogram#Examples).

Enjoy hashing it out!

## Resources

* [Intro to Hashes](http://ruby-for-beginners.rubymonstas.org/built_in_classes/hashes.html)
* [RubyMonk Hashes](http://rubymonk.com/learning/books/1-ruby-primer/chapters/10-hashes-in-ruby/lessons/46-introduction-to-ruby-hashes)
