# Subresource Integrity

In Task `10_TrustedTypes` we included the DOMPurifier from a CDN 
Let's add a SRI-Check to ensure we are loading the correct file.

Tools for generating SRI hashes
SRI Hash Generator
The [SRI Hash Generator](https://www.srihash.org/) is an online tool you can use to generate SRI hashes.

The script should still be loaded and you should still be able
to create a Trusted Type with the loaded DomPurifier.

Check what happens if you change the Hash Value a bit (by removing a sign)

### Hints

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/dompurify/2.2.7/purify.min.js" integrity="sha384-cn5CQtD1KW3XEJbmZipeNG2pq0b4WI6PXFhd83xBTcOzB0HubvrHXDkfO3kmM7oV" crossorigin="anonymous"></script>
```
