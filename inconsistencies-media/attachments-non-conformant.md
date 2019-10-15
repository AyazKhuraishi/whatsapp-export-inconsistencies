# Attachments \(Non-conformant\)

Some attachment formats do not adhere to the [standard attachment format](attachments-conformant.md#format), and will be displayed with non-standardised formatting that is often inconsistent across operating systems. This page documents all the standard deviant media formats, namely uploaded audio on Android, documents, contacts and locations.

In contrast to other attachments, non-conformant attachments cannot have messages associated with them, even though some formats on Android will use formatting that implies such.

## Uploaded audio on Android

On Android, uploaded audio leads to the format being omitted in the attachment reference. The audio file is unaffected, suggesting that this is merely a display issue.

### Format

{% tabs %}
{% tab title="Android" %}
```bash
{media}-{timestamp}-WA{id}. ({!file attached!})
```
{% endtab %}
{% endtabs %}

#### Parameters

The parameters are identical to those of a [standard attachment reference](attachments-conformant.md#parameters), spare the missing media format.

### Examples

{% tabs %}
{% tab title="Android" %}
```text
AUD-20190101-WA0000. (file attached)
```
{% endtab %}
{% endtabs %}

## Documents

On iOS, the format is quite alike a [standard attachment reference](attachments-conformant.md#format), but still includes other data like file name and page count \(On compatible documents like PDFs\) in an export with media. An export without media still includes the file name and page count, but omits the attachment reference.

On Android, the format includes only the file name and format, with the file name always being repeated on the next line as if it was a message associated with the document.

### Format

#### With media

{% tabs %}
{% tab title="iOS" %}
```bash
{filename} • {pagecount} {!page(s)!} ‎<{!attached!}: {id}-{filename}.{format}>
```
{% endtab %}

{% tab title="Android" %}
```bash
{filename}.{format} ({!file attached!})
{filename}
```
{% endtab %}
{% endtabs %}

#### Without media

{% tabs %}
{% tab title="iOS" %}
```bash
{filename} • ‎{pagecount} {!page(s)!} ‎{!document omitted!}
```
{% endtab %}

{% tab title="Android" %}
```bash
<{!Media omitted!}>
```
{% endtab %}
{% endtabs %}

#### Parameters

| Placeholder | Value |
| :--- | :--- |
| filename | File name. |
| pagecount | Page count of the document. \(iOS only\) |
| id | [Media ID](media.md#media-ids). \(iOS only\) |
| format | [Media format](media-types-and-formats.md#media-formats). |

### Examples

#### With media

{% tabs %}
{% tab title="iOS" %}
```text
test_document • ‎2 pages ‎<attached: 00000001-test_document.pdf>
```
{% endtab %}

{% tab title="Android" %}
```text
test_document.pdf (file attached)
test_document
```
{% endtab %}
{% endtabs %}

#### Without media

{% tabs %}
{% tab title="iOS" %}
```text
test_document • ‎1 page ‎document omitted
```
{% endtab %}

{% tab title="Android" %}
```text
<Media omitted>
```
{% endtab %}
{% endtabs %}

## Contacts

On iOS, the format is quite alike a standard attachment reference, but there is no media type for a contact and the format is always vCard.

On Android, the format is quite alike a standard attachment reference, but the timestamp and media ID are missing. The format also remains the same regardless of whether the chat was exported with or without media.

### Format

#### With media

{% tabs %}
{% tab title="iOS" %}
```bash
<{!attached!}: {id}-{contactname}.vcf>
```
{% endtab %}

{% tab title="Android" %}
```bash
{contactname}.vcf ({!file attached!})
```
{% endtab %}
{% endtabs %}

#### Without media

{% tabs %}
{% tab title="iOS" %}
```bash
{!‎Contact card omitted!}
```
{% endtab %}

{% tab title="Android" %}
```bash
{contactname}.vcf ({!file attached!})
```
{% endtab %}
{% endtabs %}

#### Parameters

| Placeholder | Value |
| :--- | :--- |
| contactname | First and last name of contact. |
| id | [Media ID](media.md#media-ids). \(iOS only\) |

### Examples

#### With media

{% tabs %}
{% tab title="iOS" %}
```text
‎<attached: 00000001-John Doe.vcf>
```
{% endtab %}

{% tab title="Android" %}
```text
John Doe.vcf (file attached)
```
{% endtab %}
{% endtabs %}

#### Without media

{% tabs %}
{% tab title="iOS" %}
```text
Contact card omitted
```
{% endtab %}

{% tab title="Android" %}
```text
John Doe.vcf (file attached)
```
{% endtab %}
{% endtabs %}

## Locations \(Static\)

On iOS, static locations are displayed as the name of the location preceded by a space, followed by the name of the geographical location in parentheses, a colon, a space and the Google Maps URL of the exact coordinates of the location.

On Android, static locations are displayed as the name of the location, followed by the name of the geographical location on the next line, a localised string that equates to "location" and a colon on the next line, followed by the Google Maps URL of the exact coordinates of the location.

The coordinates in the URL appear to be significantly less accurate on iOS than they are on Android. The format is always the same regardless of whether the chat was exported with or without media.

### Format

{% tabs %}
{% tab title="iOS" %}
```bash
{location} ({geographical}): https://maps.google.com/?q={latitude},{longitude}
```
{% endtab %}

{% tab title="Android" %}
```bash
{location}
{geographical}
{!location!}: https://maps.google.com/?q={latitude},{longitude}
```
{% endtab %}
{% endtabs %}

#### Parameters

| Parameter | Value |
| :--- | :--- |
| location | Name of the location. |
| geographical | Name of the geographical location. |
| latitude | Lateral coordinate of the location. |
| longitude | Longitudinal coordinate of the location. |

### Examples

{% tabs %}
{% tab title="iOS" %}
```text
 Helsinki (Helsinki): https://maps.google.com/?q=60.167850,24.952965
```
{% endtab %}

{% tab title="Android" %}
```text
Helsinki
Helsinki
location: https://maps.google.com/?q=60.167850494384766,24.952964782714844
```
{% endtab %}
{% endtabs %}

## Locations \(Live\)

On iOS, live locations are displayed with a space preceding a localised string that equates to "Location", followed, by a colon and a Google Maps URL of the exact coordinates of the users location.

On Android, live locations are displayed with a localised string that equates to "live location shared".

The format is always the same regardless of whether the chat was exported with or without media. The format does also not change depending on whether the live location is being shared or has been stopped at the time of the export.

### Format

{% tabs %}
{% tab title="iOS" %}
```bash
 ‎{!Location!}: https://maps.google.com/?q={latitude},{longitude}
```
{% endtab %}

{% tab title="Android" %}
```bash
{!live location shared!}
```
{% endtab %}
{% endtabs %}

#### Parameters

| Parameter | Value |
| :--- | :--- |
| latitude | Lateral coordinate of the location. |
| longitude | Longitudinal coordinate of the location. |

### Examples

{% tabs %}
{% tab title="iOS" %}
```text
 Location: https://maps.google.com/?q=60.167850,24.952965
```
{% endtab %}

{% tab title="Android" %}
```text
live location shared
```
{% endtab %}
{% endtabs %}

