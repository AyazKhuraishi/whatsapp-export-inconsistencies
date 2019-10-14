# User messages

User messages, in the context of this research, are the messages sent by real users. In some cases, however, a system message can look exactly like a user message - more on that [here](system-messages.md#encryption). For the sake of simplicity, this example assumes that a message was sent by a real user.

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

{% hint style="info" %}
#### Message author name

If the message author is saved in the contacts book, the author will be the full name of the contact \(First and last name\). Otherwise, the author will be the phone number of the sender.
{% endhint %}

{% hint style="warning" %}
#### Inconsistency

The format of a message timestamp is dependent on operating system, system locale and time settings.
{% endhint %}

{% hint style="warning" %}
#### Inconsistency

Message content can span multiple lines if the message includes newlines. Android additionally exhibits this behaviour with attachments; more on that [here](../inconsistencies-media/attachments-conformant.md).
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
{% endtabs %}

