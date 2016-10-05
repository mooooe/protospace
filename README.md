# Data base design

## Overview
* Users can post their own prototype
* Users can comment and like other users' post

## Tables
### Users
|id|username|e-mail|passsword|profile|avator|works|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|integer|string|string|string|string|string|string|

### Prototypes
|id|name|user_id|catch_copy|concept|like_count|image|
|:---:|:---:|:---:|:---:|:---:|:---:|
|integer|string|integer|text|text|integer|text|

### Comments
|id|user_id|prototype_id|text|
|:---:|:---:|:---:|:---:|
|integer|integer|integer|text|

### Images
|id|prototype_id|status|
|:---:|:---:|:---:|
|integer|integer|integer|

### Likes
|id|user_id|protospace_id|
|:---:|:---:|:---:|
|integer|integer|integer|

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
