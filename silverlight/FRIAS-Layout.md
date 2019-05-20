---
layout: default
title: Demo Menu XAP
lang: en
---
{% include nav-FRIA.html %}

# FRIAS Layout

Silverlight Control FRIAS can be placed with different size at the page.
In this way several different layouts can be achieved.
The user could choose a layout with the help of **DemoMenu.xap**, itself a Silverlight Control:

*Screenshot of DemoMenu.xap*<br>
![Layout](../images/FRIA-Layout.png)

What you cannot see in the Picture is the hover effect - when the user is moving the mouse from button to button.
the orange rechtangle is supposed to be FRIAS, in the desired size.

## DemoMenu.xap

It was placed on a page like so:
```html
<div id="silverlightControlHost">
<object data="data:application/x-silverlight-2," 
  type="application/x-silverlight-2" width="600" height="400">
<param name="source" value="http://www.fleetrace.org/ClientBin/DemoMenu.xap" />
<param name="background" value="white" />
<param name="minRuntimeVersion" value="4.0.50401.0" />
<param name="autoUpgrade" value="true" />
```

I have started up an older machine with Windows XP in order to take the screenshot.

At my current machine with Windows 10 there is no support for Silverlight any more, 
and the old projects cannot be loaded into Visual Studio 2019.
I could open the old projects in VS Code, but here I just wanted to see if it still works,
now that I am writing about it, `17 May 2019`.

Back to the test of DemoMenu.xap with Windows XP. The control appears on the screen ok, 
but when I click a button nothing happens.
It was expected to take me to another html page with **FRIAS.xap**, supposed to be configured to have the chosen layout,
there may or may not be other elements on the page, like normal content.

> It worked in the past.

The good new: If I call up [FRIAS-1.html](FRIAS.html) directly it still works, and that is nice.

## Vollbild (Align Client)

In order to show FRIAS as big as possible in the browser window, and to keep it big when resizing,
some `css` and `javascript` is used, like so:

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">

<head>
<meta content="text/html; charset=utf-8" http-equiv="Content-Type" />
<meta content="de" http-equiv="Content-Language"/>
<meta name="robots" content="noindex,nofollow"/>

<title>FRIAS-6</title>

<script src="javascripts/jquery-1.4.1.min.js" type="text/javascript"></script>

<style type="text/css">
   html, body {
     height:100%;
     width:100%;
     overflow:hidden;
   } 
   #silverlightControlHost {
     height:100%;
     width:100%;
     margin:-10px;
     position:absolute;
   }
</style>

<script type="text/javascript" id="SilverlightResizeScript">
$(pageReady);
function pageReady() {
$(window).resize(onWindowResize);
};
function onWindowResize() {
var b = $("body");
var d = $("#silverlightControlHost");
d.height(b.height() - d.offset().top);
d.width(b.width() - d.offset().left);
}
</script>

</head>
<body>

<div id="silverlightControlHost">
<object type="application/x-silverlight-2" width="100%" height="100%">
<param name="source" value="http://www.fleetrace.org/ClientBin/FRIAS.xap"/>
<param name="background" value="white" />
<param name="minRuntimeVersion" value="4.0.50401.0" />
<param name="autoUpgrade" value="true" />
<param name="initParams" value="at=5,dock=xy,menuLocation=http://www.fleetrace.org/DemoIndex.xml" />
<a href="http://go.microsoft.com/fwlink/?LinkID=149156&v=4.0.50401.0" style="text-decoration:none">
  <img src="http://go.microsoft.com/fwlink/?LinkId=161376" 
    alt="Get Microsoft Silverlight" style="border-style:none"/>
</a>
</object>
<iframe style="visibility:hidden;height:0;width:0;border:0px"></iframe></div>

</body>
</html>
```

This should be the layout variation FRIAS-6, according to button position 6, 
see bottom right in the picture. It still works, on the old machine with Silverlight support installed.

> But it is all about the modern variations.

I know, but I begin with some history, 
the syntax highlighting with the help of Jekyll and Rouge is beautiful don't you think?
So some *documentation* of the history should be appropriate.

By the way, did you spot the `menuLocation` parameter?
**DemoIndex.xml** here is merely another name for **EventMenu.xml**, 
and the *Event Menu* should be usable with the Angular SPA applications,
and with the desktop applications.