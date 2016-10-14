# Data base design

## Overview
* Users can post their own prototype
* Users can comment and like other users' post

## Tables
### Users
|name|group|profile|avator|works|
|:---:|:---:|:---:|:---:|:---:|
|string|string|string|string|string|

### Prototypes
|name|user_id|catch_copy|concept|like_count|image|
|:---:|:---:|:---:|:---:|:---:|:---:|
|string|integer|text|text|integer|text|

### Comments
|user_id|prototype_id|text|
|:---:|:---:|:---:|
|integer|integer|text|

### Images
|prototype_id|status|
|:---:|:---:|
|integer|integer|

### Likes
|user_id|protospace_id|
|:---:|:---:|
|integer|integer|

## asociation
### User
* has_many :prototypes
* has_many :comments
* has_many :likes

### Prototype
* belongs_to :user
* has_many :comments
* has_many :likes
* has_many :images

### Comment
* belongs_to :user
* belongs_to :prototype

### Image
* belongs_to :prototype

### Like
* belongs_to :user
* belongs_to :prototype
