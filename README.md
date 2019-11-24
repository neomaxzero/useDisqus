# useDisqus
React hook recipe to import comments from disqus

## Steps
1. Copy this snippet.
2. Use it in your project.

## Recipe

```javascript
// Comments.js
import React, { useEffect } from 'react'

const Comments = ({ fullUrl, id }) => {
  useEffect(() => {
    var disqus_config = function() {
      this.page.url = fullUrl
      this.page.identifier = id
    }
    const d = document
    const s = d.createElement('script')
    s.src = 'https://m4x-io.disqus.com/embed.js'
    s.async = true
    s.setAttribute('data-timestamp', +new Date())

    d.body.appendChild(s)
  }, [])
  return <div id="disqus_thread"></div>
}

export default Comments
```


## Use

```javascript
// Post.js
import React from 'react';
import Comments from './Comments';

const Post = () => (
<>  
  <RestOfThePost />
  <Comments />
</>
);

export default Post;

```
## Future (if someone give me a star)

- Create real hook to import. 
