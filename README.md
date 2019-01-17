# Slack Dark Mode
A user style for easy Slack theming. [CC0](http://creativecommons.org/publicdomain/zero/1.0/).

[![Reviewed by Hound](https://img.shields.io/badge/Reviewed_by-Hound-8E64B0.svg)](https://houndci.com)

## Usage

Find your Slack's application directory.   
* Windows: %homepath%\AppData\Local\slack\
* Mac: /Applications/Slack.app/Contents/
* Linux: /usr/lib/slack/ (Debian-based)

Open resources\app.asar.unpacked\src\static\ssb-interop.js   
At the very bottom, add:
```
document.addEventListener('DOMContentLoaded', function() {
  $.ajax({
    url: 'https://raw.githubusercontent.com/evox95/slack-night-mode/master/css/raw/black.css',
    success: function(css) {
      $("<style></style>").appendTo('head').html(css);
    }
  });
 });
```

**🛑 READ FIRST:** You are strongly discouraged from using a remote CSS file. It's recommended that you create your own copy. An XSS attack could put your Slack client at risk.
