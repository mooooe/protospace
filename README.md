# Data base design

## Overview
* Users can post their own prototype
* Users can comment and like other users' post

## Tables
### Users
|id|username|e-mail|passsword|member|profile|avator|works|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|integer|string|string|string|text|text|text|text|

### Protospaces
|id|user_id|catch_copy|concept|
|:---:|:---:|:---:|:---:|
|integer|integer|text|text|

### Comments
|id|user_id|protospace_id|text|
|:---:|:---:|:---:|:---:|
|integer|integer|integer|text|

### Images
|id|user_id|protospace_id|image|
|:---:|:---:|:---:|:---:|
|integer|integer|integer|integer|

### Likes
|id|user_id|protospace_id|
|:---:|:---:|:---:|
|integer|integer|integer|

## asociation
### User
* has_many :prototypes
* has_many :comments

### Prototype
* has_many :comments
* has_many :likes
* has_many :images

### Comment
* belongs_to :user
* belongs_to :prototype

### Image
* belongs_to :user

### Like
* belongs_to :user
* belongs_to :prototype
