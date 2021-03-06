# Object Orientation 

## Objective
***Students will be able to use and explain the function of objects to model real-life structures.***

## SWBATs
  + Create a class
  + Explain what object orientation is and why we use it
  + Create an instance of a class
  + Add attributes (reader and writer methods) to a class
  + Use instance variables within a class
  use correct syntax in naming classes
  + Create an initialize method to assign values to attributes when an instance is created
  + Create instance methods to have objects take action
  + Convert scripted code into object oriented code


## Motivation / Why Should You Care?
Who knows how many people are on Facebook? Close to a quarter of the world is on Facebook (roughly 2billion). What do you think the average number of friends a user has? What about the number of photos? How many likes happen in a day? We're talking about trillions of pieces of data that Facebook tracks and stores on huge tracks on land that they bought literally just to store all their data.

When you log in, how does Facebook know to your data? Your exact profile and data loaded for you and you alone, and not someone else's? How does that work? How in the world are they able to do that for 2 billion users?

Object Orientation is a way to organize, manipulate and store data. It's so powerful that it gives companies like Facebook the ability to do that - Have them name apps (Instagram, Snapchat, Square or Strip, Spotify). It's one of the most important and pervasive concepts in computer programming and supports all sorts of applications like Instagram and Facebook, to ESPN to payment apps like Amazon payment. In fact, you guys are going to build your own payment system tomorrow.

The answer is through a type of programming called object-oriented programming. It’s a way a building new objects (alien enemies, Sim people, cars, etc.) by making "factories" that standardize how the objects are made. Programmers don’t have to code every car in GTA individually, every Facebook account, or every Amazon payment. What they do is create a template for objects that can then be tailored without having to recreate all of the code for each new object. The same goes for applications like Facebook and Twitter.

## Lesson Plan
+ Create an instance of a Facebook user with a hash
```ruby
jeff = {
  :name => "Jeff",
  :email => "jeff@astor.io",
  :password => "supersecretpassword",
  :friends => 0
}
```
+ It would take forever to build a hash for each Facebook user.
  * Instead we can make a standardized template using and class.
+ Class Syntax:
```ruby
  class User
  end

  jeff = User.new
```
+ Define class and instance of a class
+ Objects have descriptors (attributes) and actions (methods)
  * List possible descriptors and actions for a Facebook user
+ Reader and writer methods
+ Instance variables
+ Initialize method
  * Have students add an initialize method to their interactive lab classes
  * Passing arguments to the initialize method
    * Have students add an argument to their initialize method
+ Create a method inside class, like `poke_friend` or `post_to_wall`
+ Everything is an object
  * The string `"hi"` is actually `String.new("hi")`
    * Shortcut is just syntactic sugar
  * Same for arrays, integers, hashes, etc.
  * We can add methods to existing classes
```ruby
  class Array
    def say_items
      puts “The items in this array are:”
      self.each do |item|
        puts item
      end
    end
  end
```


## Conclusion / So What?
Object-oriented programming is powerful for a few main reasons. First of all, when you make an instance of a class, it is its own discrete object. If you make a change to that object, it won't affect any of your other code. This is called encapsulation. Second of all, OOP allows you to have many different methods with the same name that do the same job, but on different objects. This is called polymorphism, and it keeps your code DRY. Along with this, OOP allows you to write generic code (your blueprint!), which can be used over and over again without having to rewrite the same code. All these concepts make complex code much more reliable and easier to maintain and change.

### Hints and Hurdles
+ Instead of automatically naming reader and writer methods as we normally would, give them much more descriptive names at first like `tell_me_how_much_money_I_have` or `set_my_money_to`.
+ Use writers with () first when changing an attribute. Then show that we don't need them because Ruby is friendly - and that's why we are putting the = in the name of the writer method.

```ruby
  class User
    def initialize(username, password)
      @username = username
      @password = password
    end

    def username
      @username
    end

    def username=(username)
      @username = username
    end

  end

  jeff = User.new("jastornaut", "supersecretpassword")

  # First show writer like this:

  jeff.username=("jastornaut")

  # Then explain that the above is the same as:

  jeff.username = "jastornaut"
```
+ Hit home that a writer is a statement ("Your name is Jeff") and a reader is a question ("What is your name?")
+ Get students to understand that anything can be turned into a class with attributes and actions. Pick a bunch of different items and make them say the attributes and actions for those classes.
+ Wait to introduce attr_accessor until the next class so they can really dig their teeth into how reader and writer methods work.