---
title: Tipon College's Forms
exclude: true
---

![university](img/university.jpg)

You are working for the prestigious Tipon College to meet the joint needs of _Admissions_, _Alumni Relations_, and _Communications_. People are constantly visiting campus - to see someone they know, to check out the school as a prospective student, to give a talk, to interview, to come back to the school (alumni!), or for a variety of reasons.

It would be valuable to know who is on a campus throughout the year, so you are asked to write a standard form that Tipon can give visitors to collect their information. Tipon intends to use the information from this form later on to communicate with potential donors or reach out to prospective students.

Since Tipon wants to make sure that this data is useful, they have also asked you to validate whatever information is entered into the form. That is your job.


### The Visitors
Here are a couple of examples of people who may be visiting campus:

**Vignette 1:**
> Beverly (52) and Robert (55) Deason are bringing their daughter Mary (17) for a college visit. Mary is a junior in high school, and is thinking about going to Tipon. Coming from Milwaukee, WI, the family is traveling across a number of colleges in the Midwest. Mary says that you can email her at mlp231@mac.com or text her at (414) 431-5817.

**Vignette 2:**
> Terrell Hughes is on campus to interview for the tenure-track Computer Science faculty position. He is currently a visiting scholar at Cornell University in Ithaca, NY, having been there since he got his Ph.D. from NYU a year ago. You have his business card, which lists his contact information as thughes14211@cornell.edu and (607) 151-4561. Terrel laughed when you asked for his age, and just said to put down 30.

**Vignette 3:**
> Rolf Feierabend has lived in Tipon, WI since 1961, when his parents immigrated to the US, bringing then-seventeen Rolf in tow. He has been retired for a couple of years now, and takes his husky lab Winston on walks through campus on occasion. Although he has an email account feierabend411@aol.com he doesn’t really check it anymore. He says to just call him at (920) 511-5161.

Answer the following questions:
- Which information should we collect from each visitor?
- In the context of a form, what fields will the form have?
- For each field, how can you validate the input?


### The Code

Rather than a typical online form, we'll be designing our via the command-line in Python. You've been provided a template to build off of in [validation.py](code/validation.py). We'll highlight the key parts here.


#### The Form Function
`form()` acts as the main function of the program. It's where we assign each of the fields that we would like to collect, and also where we report the collected information afterwards.

```python
def form():
  """The form function that collects info from users"""
  # Get street number
  streetNum = get_street_num()
  # Get the age
  age = get_age()

  # Collect more pieces of information by writing more functions

  # Then, print out all our collected info in a form
  print("=====================")
  print("We've collected the following information:")
  print("- Street Number:", streetNum)
  print("- Age:", age)
  # add more
  print("=====================")
```

#### Validation Functions
While there are many ways to validate input in programming languages, we'll use `if` `elif` `else` statements in order to practice conditional logic. For each field that you want to collect, you should have a corresponding validation function that you create. We've completed one for you as an example: `get_street_num()`

Conceptually, `get_street_num()` gets input from the user and then checks a couple of basic 'bad' cases (you may want to check more):
- Is the field empty?
- Is the field something other than an number?

If the user's input matches one of our bad cases, the function is repeated until the input passes all cases (when the code reaches the `else` statement below)

```python

def get_street_num():
  """ EXAMPLE: Gets the user's street number.
  Repeats until a valid street number is given.
  Output:
  - streetNum: an integer representing the user's street number
  """
  streetNum = input("Enter the street number of your address: ")

  # Check to see if it's empty!
  if streetNum == "":
    print("SORRY! You forgot to input your street number!\n")
    return get_street_num()
  # Check to see if it's a number!
  elif streetNum.isdigit() == False:
    print("SORRY! Your street number should be a positive number\n")
    return get_street_num()
  else:
    return streetNum
```

### What you should do

- First, completely the partially finished `get_age()` function. Provide suitable checks that someone has entered a reasonable age (for example, no one should be 800 years old).

- Next, create new fields (such as name, email, and phone number) and new functions to validate those fields.
  - Hint: You may find some `string` methods very useful (such as `isdigit()` used in the example to check if the string is a number). [Check out the documentation for a full list.](https://docs.python.org/3/library/stdtypes.html#string-methods)

- Once you are satisfied, move onto [the next part of this assignment...](stories)
