# Specific browser detection

In the copyright page there are large spaces of comments, inside these comments
are the following informations:

You must come from : "https://www.nsa.gov/".

Let's use this browser : "ft_bornToSec". It will help you a lot.

It is not recommended to use specific browser detection to solve bugs and
problems in a website. Mozilla recommends to check for features instead.

# Tools Insomnia application

You can make a curl request sending "ft_bornToSec" as User-Agent and
https://www.nsa.gov/ as Referer and the url of the copyright page:
http://192.168.0.8/?page=b7e44c7a40c5f80139f0a50f3650fb2bd8d00b0d24667c4c2ca32c88e13b758f

# How to solve it

Considerations before using browser detection

When considering using the user agent string to detect which browser is being used, your first step is to try to avoid it if possible. Start by trying to identify why you want to do it.

Are you trying to work around a specific bug in some version of a browser?

    Look, or ask, in specialized forums: you're unlikely to be the first to hit this problem. Also, experts, or people with another point of view, can give you ideas for working around the bug. If the problem seems uncommon, it's worth checking if this bug has been reported to the browser vendor via their bug tracking system (Mozilla; WebKit; Blink; Opera). Browser makers do pay attention to bug reports, and the analysis may hint about other workarounds for the bug.
Are you trying to check for the existence of a specific feature?

    Your site needs to use a specific Web feature that some browsers don't yet support, and you want to send those users to an older website with fewer features but that you know will work. This is the worst reason to use user agent detection because odds are eventually all the other browsers will catch up. In addition, it is not practical to test every one of the less popular browsers and test for those Web features. You should never do user agent sniffing. There is always the alternative of doing feature detection instead.
Do you want to provide different HTML depending on which browser is being used?

    This is usually a bad practice, but there are some cases in which this is necessary. In these cases, you should first analyze your situation to be sure it's really necessary. Can you prevent it by adding some non-semantic <div> or <span> elements? The difficulty of successfully using user agent detection is worth a few disruptions to the purity of your HTML. Also, rethink your design: can you use progressive enhancement or fluid layouts to help remove the need to do this?

Avoiding user agent detection

If you want to avoid using user agent detection, you have options!

Feature detection

    Feature detection is where you don't try to figure out which browser is rendering your page, but instead, you check to see if the specific feature you need is available. If it's not, you use a fallback. In those rare cases where behavior differs between browsers, instead of checking the user agent string, you should instead implement a test to detect how the browser implements the API and determine how to use it from that. An example of feature detection is as follows.

# Source
https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent

