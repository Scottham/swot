# Swot :apple:

If you have a product or service and offer **academic discounts**, there's a good chance there's some manual component to the approval process. Perhaps `.edu` email addresses are automatically approved because, for the most part at least, they're associated with American post-secondary educational institutions. Perhaps `.ac.uk` email addresses are automatically approved because they're guaranteed to belong to British universities and colleges. Unfortunately, not every country has an education-specific TLD (Top Level Domain) and plenty of schools use `.com` or `.net`.

Swot is a community-driven or crowdsourced library for verifying that domain names and email addresses are tied to a legitimate university of college - more specifically, an academic institution providing higher education in tertiary, quaternary or any other kind of post-secondary education in any country in the world.

**Pop quiz:** Which of the following domain names should be eligible for an academic discount? `stanford.edu`, `america.edu`, `duep.edu`, `strath.ac.uk`, `wunizar.es`, `usask.ca`, `hil.no`, `unze.ba`, `fu-berlin.de`, `ecla.de`, `bvb.de`, `lsmu.com`. Answers at the foot of the page.

### Usage

#### Verify Email Addresses

```ruby
Swot::is_academic? 'lreilly@stanford.edu'           # true
Swot::is_academic? 'lreilly@strath.ac.uk'           # true
Swot::is_academic? 'lreilly@soft-eng.strath.ac.uk'  # true
Swot::is_academic? 'pedro@ugr.es'                   # true
Swot::is_academic? 'lee@uottawa.ca'                 # true
Swot::is_academic? 'lee@leerilly.net'               # false
```

#### Verify Domain Names

```ruby
Swot::is_academic?('harvard.edu')               # true
Swot::is_academic?('www.harvard.edu')           # true
Swot::is_academic?('http://www.harvard.edu')    # true
Swot::is_academic?('http://www.github.com')     # false
Swot::is_academic?('http://www.rangers.co.uk')  # false
```

#### Find School Names

```ruby
Swot::school_name 'lreilly@cs.strath.ac.uk'
# => "University of Strathclyde"

Swot::school_name 'lreilly@stanford.edu'
# => "Stanford University"
```

### Contributing to Swot

Contributions welcome! Please see the [contribution guidelines](CONTRIBUTING.md) for details on how to add, update, or delete schools. Code contributions welcome too. Ports to different languages welcome too.

**Thanks** to the following people for their contributions:
@blutack, @captn3m0, @johndbritton, @johnotander, @pborreli, @rcurtis, @vikhyat,.

**Special thanks** to @weppos for the [public_suffix](https://github.com/weppos/publicsuffix-ruby) gem :metal:

### Copyright

Copyright (c) 2012 Lee Reilly. See LICENSE.txt for further details.

### Pop Quiz Answers

Hopefully, you'll be surprised by some of this:

| Domain | Academic? | Comments |
|--------|-----------|----------|
|`stanford.edu`|:heavy_check_mark:|OK, this was an easy one so you could get at least *one* right|
|`america.edu`|:heavy_multiplication_x:| Prior to October 29th 2001, anyone could register a `.edu` domain name ([details](http://en.wikipedia.org/wiki/.edu#Grandfathered_uses)) |
|`duep.edu`|:heavy_check_mark:| Alfred Nobel University is a *Ukranian* University *in the Ukraine* i.e. not in the USA :us: |
|`strath.ac.uk`|:heavy_check_mark:|The University of Strathclyde in Glasgow, Scotland|
|`unizar.es`|:heavy_check_mark:|The University of Zaragoza in Spain|
|`usask.ca`|:heavy_check_mark:|The University of Saskatchewan in Canada|
|`hil.no`|:heavy_check_mark:|Lillehammer University College in Norway|
|`unze.ba`|:heavy_check_mark:|University of Zenica in Bosnia and Herzegovina|
|`fu-berlin.de`|:heavy_check_mark:|Free University of Berlin in Germany|
|`ecla.de`|:heavy_check_mark:|ECLA of Bard is a state recognized liberal arts university in Berlin, Germany |
|`bvb.de`|:heavy_multiplication_x:|It's a soccer team from Germany|
|`lsmu.com`|:heavy_check_mark:| Lugansk State Medical University in the Ukraine |


### Known Issues / Bugs / "Features"

* You can search by email and domain names only. You cannot search by IP.
* You don't know if the email address belongs to a student, faculty, staff member, alumni, or a contractor.
* There may be a few false positives, missing institutions... maybe even a couple of typos. Contributions welcome!

![](http://i.imgur.com/K8vsw.gif)

### Preventing Abuse

Just because someone has verified that they own `lreilly@stanford.edu` doesn't mean that they're a student. They could be faculty, staff, alumnni, or maybe even an external contractor. If you're suddenly getting a lot of traffic from websites like [FatWallet](http://www.fatwallet.com) or [SlickDeals](http://www.slickdeals.net), you might want to find out why. If you're suddenly getting a lot of requests from a particular school, you should look into that too. It may be good business, word of mouth, or someone may have found a loophole.

In short, Swot gives you a high confidence level and not a guarantee. You should put some controls in place or at least monitor how's it doing from time to time.

### What is a swot?

According to [UrbanDictionary](http://www.urbandictionary.com/define.php?term=swot) :blue_book:

> A word used by morons to insult a person of superior academic abilities.

or

> [verb] To Swot; Revision undertaken preceding an examination.

or

> [anagram] Stupid Waste of Time
