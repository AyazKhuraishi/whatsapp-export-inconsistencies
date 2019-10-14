# Media types and formats

## Media types

Media types are named and used inconsistently across operating systems. IOS uses a more verbose format, whereas Android uses a shorter notation.

| Android | iOS | Description |
| :--- | :--- | :--- |
| IMG | PHOTO | Image, captured or uploaded. |
| VID | VIDEO | Video, captured or uploaded. |
| AUD | AUDIO | Audio, imported. \(iOS: Voice message\) |
| PTT | \(No equivalent\) | Voice message, recorded. |
| GIF | GIF | GIF, uploaded. |

{% hint style="warning" %}
#### Voice message type inconsistency

On iOS, a distinction is not made between uploaded audio and recorded voice messages, and the `AUDIO`format is used for both instead. On Android, only uploaded audio uses the `AUD` \(Equivalent\) format, recorded voice messages getting the `PTT` format instead.
{% endhint %}

{% hint style="warning" %}
#### GIF type and format mismatch

GIF attachments retain the `GIF` type when exported, but the file format is automatically converted to MPEG-4 video instead of a GIF image.
{% endhint %}

## Media formats

Media formats are named and used consistently across operating systems. The following formats are used per standard for the following types of data.

| Media | Format | File ending |
| :--- | :--- | :--- |
| Images | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg |
| Videos | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 |
| GIFs | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 |
| Voice messages | [Opus](https://en.wikipedia.org/wiki/Opus_%28audio_format%29) | .opus |
| Contacts | [vCard](https://en.wikipedia.org/wiki/VCard) | .vcf |

{% hint style="info" %}
#### Media re-encoding

Images and videos are automatically re-encoded by the application to the above listed formats, no matter the source format. Uploaded audio, on the other hand, is not re-encoded.
{% endhint %}

{% hint style="info" %}
#### GIF conversion

WhatsApp will convert GIF images to MPEG-4 video during export. The output video consists of a singular sequence of the GIF.
{% endhint %}

