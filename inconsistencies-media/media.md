# Media metadata

This page documents miscellaneous inconsistencies relating to media in chat exports.

## Media IDs

On iOS, a media ID is a sequence of eight numbers. This sequence is the running number of the message it was sent in, left-padded by zeroes. I.e. if the media was sent in message 28, the message ID would be `00000028`. However, at some point, this numbering appears to start falling behind the message index, and I haven't been able to find a clear reason as to why that happens. As such, this number should not be considered a reliable metric for indexing.

On Android, a media ID is a sequence of four numbers. This sequence is the running number of the attachments sent in the chat, left-padded by zeroes. I.e. the first attachment sent in a chat will have ID `0000`, the second attachment will have ID `0001` and so on. This running number is shared across media types, meaning that even if their types are different, they will still get IDs `0000` and `0001`.

It's additionally worth noting that iOS uses one-based indexing, whereas WhatsApp uses zero-based indexing. This means that on iOS, the lowest possible ID is `00000001`, while on Android the lowest possible ID is `0000`.

## Media timestamps

Media timestamps are formatted inconsistently across operating systems, but are not affected by system locale or time settings.

### Format

On iOS, media timestamps use a dashed and verbose format.

On Android, media timestamps use a concatenated and short format.

{% tabs %}
{% tab title="iOS" %}
```bash
yyyy-mm-dd-hh-mm-ss
```
{% endtab %}

{% tab title="Android" %}
```bash
yyyymmdd
```
{% endtab %}
{% endtabs %}

### Examples

#### iOS

{% tabs %}
{% tab title="With and without media" %}
```text
2019-01-01-12-00-00
```
{% endtab %}
{% endtabs %}

#### Android

{% tabs %}
{% tab title="With and without media" %}
```text
20190101
```
{% endtab %}
{% endtabs %}

