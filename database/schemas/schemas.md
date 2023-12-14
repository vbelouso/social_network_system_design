
# Schemas

## Document-Oriented NoSQL Database

```text
Table profiles {
  user_id [pk]
  name
  description
  photo_url
  city
  interests
}
```

## Relational Databases

```text
Table messages {
  message_id int [pk, increment]
  conversation_id int [ref: > conversations.conversation_id]
  chat_id int [ref: > chats.chat_id]
  user_id int [ref: > users.user_id]
  message_seen boolean
  created_at timestamp
}

Table conversations {
  conversation_id int [pk, increment]
  user_id int [ref: > users.user_id]
  text varchar
  message_seen boolean
  created_at timestamp
}

Table chats {
  chat_id int [pk, increment]
  user_id int [ref: > users.user_id]
  message_seen boolean
  created_at timestamp
}

Table posts {
  post_id int [pk, increment]
  user_id int [ref: > users.user_id]
  description varchar
  likes int
  views int
  hashtags varchar[]
  created_at timestamp
}

Table post_hashtags {
  hashtag_id int [pk, increment]
  post_id int [ref: > posts.post_id]
  hashtag varchar
}

Table post_comments {
  comment_id int [pk, increment]
  post_id int [ref: > posts.post_id]
  user_id int [ref: > users.user_id]
  comment_text varchar
  created_at timestamp
}

Table post_media {
  post_media_id int [pk, increment]
  post_id int [ref: > posts.post_id]
  media_id int [ref: > media.media_id]
}

Table media {
  media_id int [pk, increment]
  media_type media_type_enum
  media_url varchar
  file_size bigint
  created_at timestamp
}

Table message_media {
  message_media_id int [pk, increment]
  message_id int [ref: > messages.message_id]
  media_id int [ref: > media.media_id]
}

Table conversation_media {
  conversation_media_id int [pk, increment]
  conversation_id int [ref: > conversations.conversation_id]
  media_id int [ref: > media.media_id]
}


Table relationships {
  relationship_id int [pk, increment]
  from_user_id int [ref: > users.user_id]
  to_user_id int [ref: > users.user_id]
  relationship_type relationship_type_enum
  created_at timestamp
}

Enum relationship_type_enum {
  friends
  followers
  love
}

Enum media_type_enum {
  audio
  video
  photo
}
```
