# Resumable

Define a resumable task queue.


## Usage

```javascript
  var queue = new Resumable({
    key: 'doubanj-queue-' + item,
    mod: mod,
    storage: a_redis_client,
    ensure: function(list) {
      var seen = {};
      ret = queue.filter(function(arg) {
        if (!arg[0] || !arg[1]) return false;
        if (arg[1].user in seen) return false;
        seen[arg[1].user] = 1;
        return true;
      });
    }
  });
```
