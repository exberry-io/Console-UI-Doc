# API Reference

All WSS streams are based on request/response(s). The last message sent by server on the stream is `sig:1`

```json
{
  "sig": 1,
  "q": "v1/github.auth/createSession",
  "sid": 1
}
```

## Sites

All the methods associated Site management.

{% content-ref url="sites.md" %}
[sites.md](sites.md)
{% endcontent-ref %}

## Resources

All the methods associated Resource management.

{% content-ref url="resources.md" %}
[resources.md](resources.md)
{% endcontent-ref %}

{% hint style="info" %}
**Good to know:** Using the 'Page Link' block lets you link directly to a page. If this page's name, URL or parent location changes, the reference will be kept up to date. You can also mention a page – like [sites.md](sites.md "mention") – if you don't want a block-level link.
{% endhint %}
