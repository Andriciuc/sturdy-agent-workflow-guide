# Configure sturdy

## Overview
### Config file

Sturdy is super easy to configure and it's simply the most powerful CLI on the market! The configuration file will be read by sturdy when it starts. It is located in the folder shown below.

```bash
~/.config/sturdy/config.toml
```

https://github.com/Andriciuc/does-not-exist

The TTL setting allows you to control how long the cache entries should be kept. You could set it to any value, starting from version 1.2 the default is 300 seconds.

!!! note
    Edit the file with any text editor.
!!! warning
    You must restart sturdy after changing the file, otherwise your changes may not be applied.

## Settings:

* **cache_ttl** - time to live in seconds
* **log_level** - can be debug, info or warning.
* **meta data_dir** — where the meta-data is stored

# Restart

Restarting sturdy can be done with the command below:

```bash
sturdy restart
```

It is important that you should check the logs afterwards. Click [here](https://example.com/sturdy/logs) for more information.
