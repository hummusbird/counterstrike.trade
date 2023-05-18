# readme.md

## I own counterstrike.trade and will use it for real examples in this doc

### this is a legitimate URI to a file in this repository, testfile.md:

`https://github.com/hummusbird/counterstrike.trade/tree/main/skins.counterstrike.trade/testfile.md`

### this is not - It takes you to counterstrike.trade/testfile.md:

`https://github.com∕hummusbird∕counterstrike.trade∕tree∕main∕skins@counterstrike.trade/testfile.md`

try it out! copy and paste these links into your browser. Can you tell the difference?

the way this works is by replacing the forwardslash /, with a similar unicode character ∕ (U+2215). the "." in `skins.counterstrike.trade` was also replaced with an @. This is read by your browser as anything before the @ being userinfo, as if you were logging into a site, and anything after being the actual path.
imagine it as going to the site `counterstrike.trade/testfile.md` using your username `github.com∕hummusbird∕counterstrike.trade∕tree∕main∕skins`. Normally your browser should encode `@` as `%40`, but since it's not in the query string or parameters, it is not.

now imagine it was a popular github package, say React.

here's the real URI - it downloads version v0.14.10 for facebook's react:

`https://github.com/facebook/react/archive/refs/tags/0.14.10.zip`


if i owned the website 10.zip, i could create the subdomain `github.com∕facebook∕react∕archive∕refs∕tags∕0.14` for my the domain `10.zip`, and possibly serve whatever file i want to anyone that vists the site. I would replace all the forwardslashes with the ∕ character, and wouldn't even need to use the @ trick either. the final URI would be:

`https://github.com∕facebook∕react∕archive∕refs∕tags∕0.14.10.zip`

This is a security flaw with both the `.zip` TLD and the way unicode is handled with domains. Punycode is rarely used due to its inherently ugly and convoluted nature. Discord encodes URIs as the punycode equivalent for you, which does prevent misclicking deceptive domains, but means any legitimate unicode URIs are not displayed to the user correctly.

### the `.zip` TLD, alongside `.mov` should never have been sold to the public. Google should revoke and refund all .zip and .mov domains sold.