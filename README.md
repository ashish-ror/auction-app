# Mast - Technical Exercise

It is a web application that an endpoint and a view that will let a user upload a valid input file and return a list of winning auctions.

# Installation Instructions

To get the Rails server running locally:

Clone this repo

bundle install to install all required dependencies

rails db:create to create the database

rails db:migrate to run migrations

rails s to start the local server

# The Auction File

The file containing the list of bids and listings is formatted as follows.

Each line is a series of fields, separated by the pipe character (`|`). The
list of fields is as follows:

* date as UNIX epoch (integer)
* user ID of bidder or seller (integer)
* ID of item (integer) - either the item being bid on if the row is a bid, or
  of the item being listed if the row is a listing
* action - either 'BUY' or 'SELL' depending on whether the row is a bid or a listing
* if the row is a bid (i.e. action is 'BUY'), the price of the bid
* if the row is an auction listing (i.e. action is 'SELL'), the name of the item

Example item listing:
```
1627305213|11111111|2222222|SELL|toaster
```

Example bid:
```
1627305548|33333|2222222|BUY|25.10
```


# Usage Instructions

Upload the File with simple upload forum

If file is valid, you will be redirected to a page with all the winning bids

You may re-upload any other valid file, but bids will only be made for either new listings or old listings that do not have any bids against them

# Running Tests

bundle exec rspec

RSpec will run the tests, and you should see the output indicating whether the tests passed or failed.

# Corners Cut

User Logging can be done using devise gem and can be linked with each listing or bids

Instead of using SQLite database, we would typically use more robust databse like MySQL or PostgreSQL

We can add more CSS classes for defined styling and could enhance it better

We can add more comprehensive testing for user logging, error handling or performance testing

We can add more security and authentication measures preventing unauthorized access to the app 

We can add metrics to track/rate-limit auction file generation for its fair usage and preventing abuse