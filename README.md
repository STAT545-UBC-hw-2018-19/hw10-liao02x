# STAT545 HW10

This repo is for STAT545 Homework 10 by Minzhi Liao.

## Introduction
Tried a few things including using `RCurl`, API, `POST`.

The scrape data part is here: [scrape_data](https://raw.githack.com/STAT545-UBC-students/hw10-liao02x/master/scrape_data.html)

The API queries part is here: [api_queries](https://raw.githack.com/STAT545-UBC-students/hw10-liao02x/master/api_queries.html)

And the created issue is here: https://github.com/STAT545-UBC-students/hw10-liao02x/issues/2

## Issues in this assignment
After tried a few hours, finally I found the reason. So if you are reading this, *REMEMBER* DON'T use `jsonlite::toJSON` to convert the post content to json because it produced something not supported by github.

The required JSON should be like this:
```
{"title":"This is a title", "body":"This is a body"}
```
But `jsonlite::toJSON` produces somthing like this:
```
{"title":["This is a title"], "body":["This is a body"]}
```
This is not acceptable by github, and it waste me a lot of time. I'm adding a issue to that.
