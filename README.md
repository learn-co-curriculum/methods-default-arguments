# Methods with Default Arguments

## Objectives

1. Define options arguments. 
2. Understand when and why to use them. 
3. Learn how to define a method to take in optional arguments. 
4. Call a method with and without it's optional arguments. 

## Why Optional Arguments?

We should constantly strive for our code to be dynamic and flexible. As programmers, we are lazy (which is a virtue). Consequently, we want the code we write to be re-usable. 

If we define a method, `#greeting`, like this:

```ruby
def greeting
  puts "Hello, Ruby programmer!"
end
```

We have to re-define or re-write that method every time we'd like to use it greet someone else. That is way to much work for us. Instead, we'll define our method to take in an *argument* of someone's name:

```ruby
def greeting(name)
  puts "Hello, #{name}"
end
```

Now our method is flexible and dynamic, it can be used again and again to greet different people. 

But what if we don't know the name of the person we are trying to greet? We can make this method even more flexible by making the `name` argument optional. How do we do this? With optional, or default, arguments. 

## Default Arguments

In order to define a method that optionally takes in an argument, we define our method to take in an argument with a **default value**. By defining out method with default arguments, we make it possible to call the method with optional arguments, i.e. with or without arguments. 

```ruby
#             assigning a default value
def greeting(name = "Ruby programmer")
  puts "Hello, #{name}"
end
```

In our argument list, `(name = "Ruby programmer")`, we simply assign the argument `name` a default value of `"Ruby programmer"`. By doing so, we are really saying:

If the method is invoked without any arguments, i.e. like this: `greeting`, Ruby will assume the value of the `name` variable inside the method to be `"Ruby programmer"`. 

However, if the method is invoked with an argument, `greeting("Sophie")`, Ruby will assign the variable `name` to the string `"Sophie"` inside the method. 

```ruby
greet
  => Hello, Ruby programmer!

greet("Sophie")
  => "Hello, Sophie!"
```

With default arguments our once simple machine becomes profoundly useful and abstract:

## Adding Default Arguments

Default arguments are easy to add, you simply assign them a default value with `=` ("equals") in the argument list. There's no limit to the amount of arguments that you can make default.

```ruby
def greeting_programmer(name="Ruby programmer", language="Ruby")
	puts "Hello, #{name}. We heard you are a great #{language} programmer."
end
```

Let's take a look at the different ways we can call this method:

```ruby
greeting
  => Hello, Ruby programmer. We heard you are a great Ruby programmer. 

greeting("Sophie")
  => Hello, Sophie. We heard you are a great Ruby programmer. 

greeting("Steven", "Elixir")
  => Hello Steven. We heard you are a great Elixir programmer.
```

## Conclusion

Method arguments, both required and optional, make methods powerfully abstract and dynamic machines that are easy to build yet very flexible and adaptable to different situations and requirements. Get used to defining methods with required and default arguments and calling them correctly.
