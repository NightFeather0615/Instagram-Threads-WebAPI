# Instagram Threads WebAPI


## Info
This docs is based on unofficial HTTP unpacking (for education purpose), use at your own risk.  
Unpack Tools: `HTTP Toolkit`, `Android QEMU`, `Frida`

Base URL: `i.instagram.com/api/v1`  
Base Header:
```
User-Agent: Barcelona 289.0.0.77.109 Android (33/13; 420dpi; 1080x2337; Google/google; sdk_gphone64_arm64; emu64a; ranchu; en_US; 489720145)
Authorization: Bearer IGT:2:<sercet>
Host: i.instagram.com
```


## Endpoints

### POST `/notifications/badge`
Usage: Get notification count.  
Tips: `device_id` or `phone_id` must be filled in, can fill with any non-blank string.  
Request Body (`application/x-www-form-urlencoded`):
```
user_ids: <user_id>
device_id: <optional<uuid>>
phone_id: <optional<uuid>>
_uuid: <optional<uuid>>
```

---

### POST `/qp/batch_fetch`
Usage: Unknown.  
Request Body (`application/x-www-form-urlencoded`):
```
signed_body: <string>
```

---

### POST `/feed/text_post_app_timeline`
Usage: Get user timeline.  
Tips: `pagination_source` should be `text_post_feed_threads`.  
Request Body (`application/x-www-form-urlencoded`):
```
pagination_source: <string>
```

---

### POST `/text_feed/text_app_inbox_seen`
Usage: Mark inbox as read.  
Request Body (`application/x-www-form-urlencoded`):
```
_uuid: <optional<uuid>>
```

---

### GET `/text_feed/recommended_users`
Usage: Get recommended users. 

---

### GET `/text_feed/text_app_notifications`
Usage: Get notifications.  
URL Params:
```
feed_type: <optional<string>>
mark_as_seen: <optional<bool>>
timezone_offset: <optional<int>>
timezone_name: <optional<string>>
```

---

### Get `/text_feed/link_preview`
Usage: Fetch link's Open Graph data.  
URL Params:
```
url: <string>
```

---

### GET `/text_feed/<post_id>/replies`
Usage: Get post replies.

---

### GET `/text_feed/<user_id>/profile`
Usage: Get user's posts.

---

### GET `/text_feed/<user_id>/profile/replies`
Usage: Get user's replies.

---

### POST `/media/<post_id>/like`
Usage: Like a post.  
Request Body (`application/x-www-form-urlencoded`):
```
signed_body: <optional<string>>
d: <optional<int>>
```

---

### POST `/media/<post_id>/unlike`
Usage: Unlike a post.  
Request Body (`application/x-www-form-urlencoded`):
```
signed_body: <optional<string>>
d: <optional<int>>
```

---

### GET `/users/<user_id>/info`
Usage: Get user info.  
URL Params:
```
is_prefetch: <optional<bool>>
entry_point: <optional<string>>
from_module: <optional<string>>
timezone_name: <optional<string>>
```

---

### GET `/users/search`
Usage: Search user.  
URL Params:
```
q: <string>
count: <optional<int>>
search_surface: <optional<string>>
timezone_offset: <optional<int>>
```

---

### GET `/friendships/show/<user_id>`
Usage: Show specified user's friendship info.

---

### POST `/friendships/create/<user_id>`
Usage: Create friendship with specified user.  
Request Body (`application/x-www-form-urlencoded`):
```
signed_body: <optional<string>>
```

---

### POST `/friendships/destroy/<user_id>`
Usage: Destroy friendship with specified user.  
Request Body (`application/x-www-form-urlencoded`):
```
signed_body: <optional<string>>
```

---

### POST `/repost/create_repost`
Usage: Repost a post.  
Request Body (`application/x-www-form-urlencoded`):
```
media_id: <string>
_uuid: <optional<uuid>>
```

---

### POST `/warning/check_offensive_multi_text`
Usage: Content offensive checking.  
Request Body (`application/x-www-form-urlencoded`):
```
signed_body: <string>
```

---

### POST `/media/configure_text_only_post`
Usage: Create/configure text post.  
Request Body (`application/x-www-form-urlencoded`):
```
signed_body: <string>
```

---

### POST `/media/<post_id>/delete`
Usage: Delete a post.  
URL Params:
```
media_type: <optional<string>>
```

---

### GET `/media/<post_id>/permalink`
Usage: Get post's permalink.  
URL Params:
```
exposed_to_experiment: <optional<bool>>
inventory_source: <optional<string>>
share_to_app: <optional<string>>
m_t: <optional<int>>
containermodule: <optional<string>>
```
