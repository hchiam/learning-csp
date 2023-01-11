# Learning about CSP (Content Security Policy)

Just one of the things I'm learning. <https://github.com/hchiam/learning>

![example CSP meta tag](https://github.com/hchiam/learning-csp/blob/master/example-csp.png "example CSP meta tag")

<https://developers.google.com/web/fundamentals/security/csp>

- source whitelisting
- avoid inline code = best practice anyways, and improves caching, readability, compilation, and minification
- block everything with default-src 'none' and then build up from there, only what you allow:

## Want to see a live demo and play with the code?

<https://codepen.io/hchiam/pen/vYNWGrj>

## Just want to copy and paste some code?

_**Triple**_-click to select all:

```html
<meta
  http-equiv="Content-Security-Policy"
  content="default-src 'none'; script-src https://developers.google.com; style-src https://developers.google.com; img-src https://developers.google.com; connect-src https://developers.google.com; child-src 'self'"
/>
```

(Replace `https://developers.google.com` with your trusted source(s).)

## Quickly check your CSP

<https://csp-evaluator.withgoogle.com/>

## A quick note on [SRI (Subresource integrity)](https://www.smashingmagazine.com/2019/04/understanding-subresource-integrity)

```html
Content-Security-Policy: require-sri-for script
```

## More info on CSP

https://portswigger.net/web-security/cross-site-scripting/content-security-policy

https://portswigger.net/web-security/clickjacking#:~:text=against%20clickjacking%20attacks.-,Content%20Security%20Policy,-(CSP) (look for the "Content Security Policy" section)

```html
Content-Security-Policy: frame-ancestors 'none';
```

- is like the response header `X-Frame-Options: deny` (which you should use for older browsers).

```html
Content-Security-Policy: frame-ancestors 'self';
```

- is like the response header `X-Frame-Options: sameorigin` (which you should use for older browsers).

```html
Content-Security-Policy: frame-ancestors normal-website.com;
```

- is like the response header `X-Frame-Options: allow-from https://normal-website.com` (which you should use for older browsers).
