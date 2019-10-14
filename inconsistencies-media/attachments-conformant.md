# Attachments \(Conformant\)

Attachment references link to media that has been sent in a chat. Chats can be exported in two formats, with and without media. The exact behaviour of attachment references between these two formats is also inconsistent, described in detail below.

{% hint style="warning" %}
#### Inconsistency

This section only documents the media formats that conform to the attachment format, namely photos, videos, GIFs and most audio. Other formats deviate from this, however, and they are documented on the [Attachments \(Non-conformant\)](attachments-non-conformant.md) page.
{% endhint %}

### Format

On iOS, in a media-including export, an attachment is surrounded by arrows, followed by a localised string which equates to "attached", a colon, a space and a reference to the attachment file. In a media-less export, an attachment is displayed as an otherwise unmarked localised string that equates to "media omitted". IOS displays the type of the media that was omitted with a localised string.

On Android, in a media-including export, an attachment is displayed as a reference to the attachment file, followed by a phrase in parentheses which equates to "file attached". In a media-less export, an attachment is displayed as a pair of arrows containing a localised string that equates to "media omitted". Android does not display the type of the media that was omitted.

If an attachment has a message associated with it, Android will display it on the line below the attachment reference, but only in the event that the chat was exported with media. IOS never includes the associated message.

{% hint style="info" %}
#### Localisation

Attachment references are always localised.
{% endhint %}

#### iOS

{% tabs %}
{% tab title="With media" %}
```bash
‎<{!attached!}: {id}-{media}-{timestamp}.{format}>
```
{% endtab %}

{% tab title="Without media" %}
```bash
{!{medianame} omitted!}
```
{% endtab %}
{% endtabs %}

#### Android

{% tabs %}
{% tab title="With media" %}
```bash
{media}-{timestamp}-WA{id}.{format} ({!file attached!})
```
{% endtab %}

{% tab title="Without media" %}
```bash
<{!Media omitted!}>
```
{% endtab %}
{% endtabs %}

#### Parameters

| Parameter | Value |
| :--- | :--- |
| id | [Media ID](media.md#media-ids). |
| media | [Media type](media-types-and-formats.md#media-types). |
| medianame | Localised media type name. Can equate to "image", "video", "audio" or "GIF". IOS only. |
| timestamp | Timestamp of when this attachment was sent. |
| format | [Media format](media-types-and-formats.md#media-formats). |

{% hint style="warning" %}
#### Inconsistency

Media IDs are inconsistent across operating systems.
{% endhint %}

{% hint style="warning" %}
#### Inconsistency

Media timestamps are inconsistent across operating systems, but not system locale or time settings.
{% endhint %}

{% hint style="warning" %}
#### Inconsistency

Media types and formats are inconsistent across operating systems.
{% endhint %}

### Examples

#### iOS

{% tabs %}
{% tab title="With media" %}
```text
‎<attached: 00000001-PHOTO-2019-01-01-12-00-00.jpg>
<attached: 00000002-VIDEO-2019-01-01-12-00-00.mp4>
<attached: 00000003-AUDIO-2019-01-01-12-00-00.opus>
<attached: 00000004-AUDIO-2019-01-01-12-00-00.mp3>
<attached: 00000005-GIF-2019-01-01-12-00-00.mp4>
```
{% endtab %}

{% tab title="Without media" %}
```text
image omitted
video omitted
audio omitted
audio omitted
GIF omitted
```
{% endtab %}
{% endtabs %}

#### Android

{% tabs %}
{% tab title="With media" %}
```text
IMG-20190101-WA0000.jpg (file attached)
VID-20190101-WA0001.mp4 (file attached)
PTT-20190101-WA0000.opus (file attached)
AUD-20190101-WA0000.mp3 (file attached)
GIF-20190101-WA0000.mp4 (file attached)
```
{% endtab %}

{% tab title="Without media" %}
```text
<Media omitted>
<Media omitted>
<Media omitted>
<Media omitted>
<Media omitted>
```
{% endtab %}
{% endtabs %}

