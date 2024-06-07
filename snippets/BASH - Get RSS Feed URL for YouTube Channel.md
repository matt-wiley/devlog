# [[BASH - Get RSS Feed URL for YouTube Channel]]

```bash
#!/usr/bin/env bash

function main {
  #
  # Given a YouTube channel URL, this script will echo out the RSS feed URL for that channel.
  #
  local channel_id=$(curl -sSL "${1}" | grep -oE "https://www.youtube.com/channel/[^ \"]+" | head -n1 | grep -oE "[^/]+$")
  echo "https://www.youtube.com/feeds/videos.xml?channel_id=${channel_id}"
}
main "${@}"
```

