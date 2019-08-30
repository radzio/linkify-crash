# linkify-crash
Sample project for demo an issue with Linkify

When autoLink property is set to "all" and I set an address with unicode characters it crashes. 

```
 Caused by: java.lang.NumberFormatException: For input string: "𝟏𝟏"
        at java.lang.Integer.parseInt(Integer.java:615)
        at java.lang.Integer.parseInt(Integer.java:650)
        at android.webkit.FindAddress.checkHouseNumber(FindAddress.java:272)
        at android.webkit.FindAddress.matchHouseNumber(FindAddress.java:304)
        at android.webkit.FindAddress.attemptMatch(FindAddress.java:396)
        at android.webkit.FindAddress.findAddress(FindAddress.java:468)
        at android.webkit.WebView.findAddress(WebView.java:1869)
        at android.text.util.Linkify.gatherMapLinks(Linkify.java:810)
        at android.text.util.Linkify.addLinks(Linkify.java:278)
        at android.text.util.Linkify.addLinks(Linkify.java:244)
        at android.widget.TextView.setText(TextView.java:5666)
```
Example address to reproduce: 80𝟏 𝟏𝟏th Avenue Sunnyvale, CA 94089
