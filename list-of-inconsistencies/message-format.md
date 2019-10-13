# Messages

Messages can have one of two senders, user and system. This section only documents user messages; system messages are documented on the page linked below.

{% page-ref page="../other-findings/system-messages.md" %}

### Format

On iOS, the message timestamp is surrounded by brackets, followed by a space and the author name. The author name is followed by a colon, a space and the message content.

On Android, the message timestamp is separated from the author name using a spaced dash. The author name is followed by a colon, a space and the message content.

{% tabs %}
{% tab title="iOS" %}
```bash
[{timestamp}] {author}: {message}
```
{% endtab %}

{% tab title="Android" %}
```bash
{timestamp} - {author}: {message}
```
{% endtab %}
{% endtabs %}

#### Parameters

| Parameter | Value |
| :--- | :--- |
| timestamp | Timestamp of when the message was sent. |
| author | Message author. |
| message | Message content. |

{% hint style="warning" %}
#### Inconsistency

The format of the timestamp is dependent on system locale and time zone.
{% endhint %}

{% hint style="warning" %}
#### Inconsistency

If the message author is saved in the contacts book, the author will be the full name of the contact \(First and last name\). Otherwise, the author will be the phone number of the sender.
{% endhint %}

{% hint style="warning" %}
#### Inconsistency

Message content can span multiple lines if the message includes newlines. Android additionally exhibits this behaviour with attachments; more on that [here](attachments.md).
{% endhint %}

### Examples

#### iOS

{% tabs %}
{% tab title="Individual and group" %}
```text
[1.1.2019, 12.00.00] John Doe: ‎Hello 😄
[1.1.2019, 12.00.00] Jane Doe: Hey!
P.S. Nice emoji 👀
[1.1.2019, 12.00.00] +1 (000) 000-0000: Good day!
```
{% endtab %}
{% endtabs %}

#### Android

{% tabs %}
{% tab title="Individual and group" %}
```text
2019-01-01 12:00 - John Doe: Hello 😄
2019-01-01 12:00 - Jane Doe: Hey!
P.S. Nice emoji 👀
2019-01-01 12:00 - +1 (000) 000-0000: Good day!
```
{% endtab %}

{% tab title="" %}

{% endtab %}
{% endtabs %}

