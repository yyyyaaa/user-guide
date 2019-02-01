---
id: pixels
title: Pixels
sidebar_label: Pixels
---

To add static pixel to the webpage you should copy script from the ads page

![](assets/pixel/copy-script.png)

An example of the img pixel :
 
```
<img src="https://adverse.lincx.la/convert?adId=8wc09d&adverseClickID=CLICK_ID&price=CHANGE_PRICE"/>
```

you should remove `&adverseClickID=CLICK_ID` from the query and change `CHANGE_PRICE` to desired value e.g. if price is $1.
So pixel img tag will be
```
<img src="https://adverse.lincx.la/convert?adId=8wc09d&price=1"/>
```

If you have the technical resources available to implement the server-side calls you can use postback tracking.

http GET request should be made to `https://adverse.lincx.la/convert` with `adverseClickId` and `price` in a query.
 
For example if price=5 and adverseClickId=cjrm4fs1d00004spp1hsfljhe

```
https://adverse.lincx.la/convert?adverseClickId=cjrm4fs1d00004spp1hsfljhe&price=5
```
