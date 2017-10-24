# Slack-Dark-Mode

[Slack Night Mode by laCour](https://github.com/laCour/slack-night-mode) theme reposted in a css version compatible with Slack for Desktop.

Append to your `Slack.app/Contents/Resources/app.asar.unpacked/src/static` the following code:

```
start(assignIn({}, require('electron').remote.getGlobal('loadSettings'), { windowType: 'WEBAPP' }));
document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'FILE_URL',
   success: function(css) {
     $("<style></style>").appendTo('head').html(css);
   }
 });
});
```
and replace `FILE_URL` with your file url path (e.g. for me is https://raw.githubusercontent.com/mattiacantalu/Slack-Dark-Mode/master/dark-mode.css).
