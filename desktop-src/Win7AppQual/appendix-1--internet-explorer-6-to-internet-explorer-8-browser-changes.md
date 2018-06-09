---
Description: The following table describes changes between Microsoft Internet Explorer 6 and Windows Internet Explorer 8.
ms.assetid: 5A7DDFC4-69A4-4B5A-9C0A-6172E2142494
title: 'Appendix 1: Internet Explorer 6 to Internet Explorer 8 browser changes'
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Appendix 1: Internet Explorer 6 to Internet Explorer 8 browser changes

The following table describes changes between Microsoft Internet Explorer 6 and Windows Internet Explorer 8.



Design changes from Internet Explorer 6 to Internet Explorer 7

Design changes from Internet Explorer 7 to Internet Explorer 8

${ROWSPAN2}$Internet Explorer versioning${REMOVE}$  

Check for code that incorrectly special cases around Internet Explorer 6, Windows Internet Explorer 7, or Internet Explorer 8 through [user-agent string sniffing, versions vectors, or conditional comments](d8013c4e-80d3-46ea-90e9-0bcacfd98b59).

-   When a long User Agent (UA) String encounters a server that accepts only shorter UA Strings, users see [an error page](http://go.microsoft.com/fwlink/p/?linkid=204992).

<!-- -->

-   The Compatibility View in Internet Explorer 8, which is turned on by default for intranet sites, sends a Internet Explorer 7 user agent string. To differentiate between Internet Explorer 7 and Compatibility View, look for the new [Trident token](http://go.microsoft.com/fwlink/p/?linkid=158312).

${ROWSPAN3}$ Standards compliance updates

-   Applies to [specified document modes](273c0385-2149-4861-bf60-3eddce6eba8a).
-   [Internet Explorer 8 Compatibility View mode](http://go.microsoft.com/fwlink/p/?linkid=204995), which is on by default for intranet sites, typically [reverts standards updates from Internet Explorer 7 to Internet Explorer 8](http://go.microsoft.com/fwlink/p/?linkid=204994).
-   Use the [EmulateIE7 X-UA-Compatible](https://www.bing.com/search?q=EmulateIE7+X-UA-Compatible) HTTP header or **meta** element to enable Compatibility View on websites or specific webpages.

${REMOVE}$  

Quirks mode exception: You do not need to make standards compliance changes for webpages that specify the quirks mode DOCTYPE (by setting the “standards-compliance” DOCTYPE switch to “off”).

Applies to Internet Explorer 7 Standards or “Strict” mode and above:

-   [XML prologs](https://www.bing.com/search?q=XML+prologs) in the first line of the source code no longer cause DOCTYPE declarations to fail.
-   [Box model](https://www.bing.com/search?q=Box+model) overflow content intersects box and no longer automatically -grows the box div to fit the content.
-   [Certain CSS filters](https://www.bing.com/search?q=Certain+CSS+filters) (for example, \*HTML, \_underscore, and /\*\*/ comment) are not supported.
-   [Only the outermost OBJECT element in nested objects](13acc0e2-c635-4c94-8723-ae72cf8b6730) is instantiated .
-   [Applications that rely on the SELECT element](13acc0e2-c635-4c94-8723-ae72cf8b6730) to get an HWND to use with Microsoft Win32 APIs might break because the [SELECT element](http://go.microsoft.com/fwlink/p/?linkid=204996) is now a windowless control.
-   [Channel Definition Format (CDF)](http://go.microsoft.com/fwlink/p/?linkid=204997) is not supported, in favor of RSS feeds.
-   [XBM](http://go.microsoft.com/fwlink/p/?linkid=204997), an imaging format that is designed for X-based systems, is not supported.
-   [BASE tags](http://go.microsoft.com/fwlink/p/?linkid=204997) outside of the HEAD document are not allowed.

Applies to Internet Explorer 8 Standards mode and above:

-   [Unclosed P elements](https://www.bing.com/search?q=Unclosed+P+elements) are automatically closed when they are followed by [**TABLE**](27bad129-af87-4cb2-ae42-638185a16b9c), [**FORM**](02e2e19e-63d3-4c81-aeee-2f37686e4cd0), [**NOFRAMES**](319046db-2095-4040-bee3-b8048f485352), or [**NOSCRIPT**](6211aae3-f046-463b-8434-bb913462d8f7) elements.
-   [Malformed HTML](http://go.microsoft.com/fwlink/p/?linkid=204994) is not supported, in favor of well-formed, valid markup.
-   The ["className" attribute](http://go.microsoft.com/fwlink/p/?linkid=204994) syntax is not supported, in favor of “class” syntax.
-   [The attributes collection](http://go.microsoft.com/fwlink/p/?linkid=204994) does not contain all possible attributes that Windows Internet Explorer recognizes.
-   [Attribute ordering has changed](http://go.microsoft.com/fwlink/p/?linkid=204994), affecting attributes collection, innerHTML, and outerHTML.
-   [GetElementById](http://go.microsoft.com/fwlink/p/?linkid=204994) is case-sensitive and does not search name attributes.
-   [Generic CSS prefix selectors](http://go.microsoft.com/fwlink/p/?linkid=204994) (that is, v\\:\* syntax) are not supported, in favor of explicit tag names.
-   [CSS expressions](http://go.microsoft.com/fwlink/p/?linkid=204994) are not supported, in favor of improved CSS support or DHTML logic.
-   Code that is intended for custom JSON object methods might conflict with the [new native JSON object](http://go.microsoft.com/fwlink/p/?linkid=204994) in Internet Explorer 8.
-   [Unset initial properties](http://go.microsoft.com/fwlink/p/?linkid=204994) on the currentStyle object return their initial value.
-   [Unspecified properties values](http://go.microsoft.com/fwlink/p/?linkid=204994) on the currentStyle object style object return an empty string (for example, see the [ASP.NET Menu and IE8 rendering white issue](http://go.microsoft.com/fwlink/p/?linkid=204999) blog post).

<!-- -->

-   For sites and applications where accessibility is a concern, update [ARIA syntax across all Internet Explorer rendering modes](http://go.microsoft.com/fwlink/p/?linkid=205000).
-   Check the [complete list of CSS updates from Internet Explorer 6 to Internet Explorer 8](https://www.bing.com/search?q=complete+list+of+CSS+updates+from+Internet+Explorer+6+to+Internet+Explorer+8).

Security improvements

-   Apply regardless of document mode.
-   You can turn off security features by using [Group Policy](http://go.microsoft.com/fwlink/p/?linkid=205006).

<!-- -->

-   The [window.opener](http://go.microsoft.com/fwlink/p/?linkid=204997) bypass to the window.close prompt is not allowed.
-   [Object caching protection](d20d2b86-aa93-4dc3-ad4c-568d3b4a9dbb) is enabled by default, which blocks access to references of objects when users browse to a new domain (applies to Internet Explorer 6 and later versions on Windows XP with Service Pack 2 (SP2) and later versions).
-   [DHTML scriptlets](d20d2b86-aa93-4dc3-ad4c-568d3b4a9dbb) are disabled by default.
-   [Scripts that write to the status bar](d20d2b86-aa93-4dc3-ad4c-568d3b4a9dbb) are blocked.
-   [URL creation might fail](https://www.bing.com/search?q=URL+creation+might+fail) if URLs do not meet RFC guidelines.
-   [HTTPS pages display an error page](https://www.bing.com/search?q=HTTPS+pages+display+an+error+page) if the site is configured to SSLv2 only, or if the site security certificate is outdated or invalid, has errors, or has weak ciphers.
-   Only ["Punycode" encoded internationalized domain names](https://www.bing.com/search?q="Punycode"+encoded+internationalized+domain+names) are supported. Other formats like ANSI and UTF-8 are blocked.
-   [Cross-domain script URLs](https://www.bing.com/search?q=Cross-domain+script+URLs), redirected navigation in DOM objects, and frame navigations are blocked.
-   [Modal or modeless dialog boxes](http://go.microsoft.com/fwlink/p/?linkid=204997) that are created from script might seem [slightly bigger](http://go.microsoft.com/fwlink/p/?linkid=205009).
-   [Unsecure protocols](http://go.microsoft.com/fwlink/p/?linkid=204997) view-source, Gopher (at the WinINET level), and Telnet do not work.

<!-- -->

-   [XSS filter](http://go.microsoft.com/fwlink/p/?linkid=205001) is on by default, which blocks script patterns that most frequently resemble Type-1 XSS attacks, unless you disable them through a X-XSS-Protection HTTP header.
-   Cross-domain, cross-document communication hacks like [SCRIPT SRC](http://go.microsoft.com/fwlink/p/?linkid=205002) are not supported, in favor of safer [XDM and XDR AJAX features](http://go.microsoft.com/fwlink/p/?linkid=205003).
-   AJAX-enabled sites that [manually manipulate the hash of the URL](463baec4-24a5-491a-bfa9-6266fbcd0187) might be broken by the new window.location.hash navigation property.
-   [New AJAX features](https://www.bing.com/search?q=New+AJAX+features) like [XDM](http://go.microsoft.com/fwlink/p/?linkid=205003) have [**native properties**](b964ce45-31ce-44b4-9b07-bb618d918f84) that might conflict with existing custom properties.
-   [File upload control](http://go.microsoft.com/fwlink/p/?linkid=205003) submits only the file path, not the full path, to the server.
-   HTML code or script that is delivered with an ["image/\*" MIME type](http://go.microsoft.com/fwlink/p/?linkid=205003) is blocked from executing.
-   [Navigating a top-level frame](7600aade-cfaa-489c-bfac-6cf610fe225c) to a site in a different security context opens a new window or tab instead of navigating within the existing frame.
-   [UTF-7 encoded script](db129e7a-c12d-46c2-ab30-ca9a8fa805cd) is forced into Windows-1252 encoding, which might cause plain text rendering.
-   [HTTP/HTTPS "mixed mode" pages](http://go.microsoft.com/fwlink/p/?linkid=205007) display a dialog box that defaults to displaying secure items only (versus the previous nonsecure default). Users might mistakenly [choose to block HTTP elements](http://go.microsoft.com/fwlink/p/?linkid=205007), like key images.
-   [DEP/NX is on by default](http://go.microsoft.com/fwlink/p/?linkid=205008), which blocks certain add-ons (that is, ActiveX controls and COM objects) that are built by using older versions of ATL from running code that is marked "non-executable" in memory.
-   [Content that is returned by a web proxy](22c7f2db-e0ab-4a5d-9def-93946a9749f4) is blocked if an SSL tunnel is not established in response to a CONNECT request to the original server.

Architectural changes

-   Apply regardless of document or compatibility mode.

<!-- -->

-   [Protected Mode](http://go.microsoft.com/fwlink/p/?linkid=205010) is enabled by default for [Internet, Intranet, and Restricted Sites zones](c8711577-a638-4093-80fb-a24c1ca72024). This mode [blocks browser extensions that could pose a security risk](69a6eff5-0670-4bea-bbc9-15bf957841c7) from running and [lower privilege applications from accessing higher privilege processes](931175be-e107-4669-b8c7-b2fcd76fb759), like the Start menu, Control Panel, and the Microsoft Windows registry (applies to Internet Explorer 7 and later versions on Windows Vista and later versions).

<!-- -->

-   [Protected Mode Update](b83ea41b-db38-4e6f-b434-e0afba82e82c): Intranet runs in medium (instead of low) integrity level by default.
-   [Loosely Coupled Internet Explorer](http://go.microsoft.com/fwlink/p/?linkid=205012) might block add-ons (that is, ActiveX controls and COM objects) that do one of the following:
    -   Use windows hierarchy techniques to locate UI frame and tab windows (which now run in separate processes at different integrity levels).
    -   Create a subclass of the UI frame (now at medium integrity level) from a low-integrity tab process.
    -   Use unsupported messaging techniques between UI frame and tabs.



 

## Related topics

<dl> <dt>

[Addressing Application Compatibility When Migrating to Internet Explorer 8](addressing-application-compatibility-when-migrating-to-internet-explorer-8.md)
</dt> </dl>

 

 


