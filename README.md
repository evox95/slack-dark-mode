# Slack Dark Mode

![](https://camo.githubusercontent.com/a01e148f7743dd4dd046ce8eb1328311cf2e2b9f/68747470733a2f2f757365727374796c65732e6f72672f7374796c655f73637265656e73686f74732f3131373437355f61667465722e706e67 "")

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
