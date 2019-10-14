# System messages

There are two types of system messages: Generic and encryption.

{% hint style="info" %}
#### Localisation

System messages are always localised.
{% endhint %}

## Generic

Generic system messages are emitted in group chats only when non-encryption related events occur. This includes addition or removal of members, changing of admin status of the user, changing of group image and description and so on. Generic system messages are identifiable in the application by their blue badge.

![An example of a generic system message](../.gitbook/assets/generic-sysmsg.png)

In exports, generic system messages can be distinguished as messages with a timestamp that lack an author and a separator between message metadata and content.

### Format

{% tabs %}
{% tab title="iOS" %}
```bash
[{timestamp}] {message}
```
{% endtab %}

{% tab title="Android" %}
```bash
{timestamp} - {message}
```
{% endtab %}
{% endtabs %}

#### Parameters

See [Messages =&gt; Parameters](message-format.md#format).

### Examples

#### iOS

{% tabs %}
{% tab title="Group" %}
```text
[1.1.2019, 12.00.00] ‎You created group "John, Jill, Joe"
```
{% endtab %}
{% endtabs %}

#### Android

{% tabs %}
{% tab title="Group" %}
```text
2019-01-01 12:00 - ‎You created group "John, Jill, Joe"
```
{% endtab %}
{% endtabs %}

## Encryption

Encryption system messages are emitted in both individual and group chats when encryption-related events occur. This includes an initial notification informing participants that messages in the chat are secured with end-to-encryption and a notification when a contact's security code changes. Encryption system messages are identifiable in the application by their yellow badge.

![](../.gitbook/assets/encryption-sysmsg.png)

On iOS, encryption system messages are impossible to distinguish from user messages as they use the same format as [user messages](message-format.md#format). In individual chats, the author is set to be the other party in the chat. In group chats, the author is set to be the group itself.

On Android, encryption system messages use the same format as a generic system message.

### Examples

#### iOS

{% tabs %}
{% tab title="Individual" %}
```text
[1.1.2019, 12.00.00] John, Jill, Joe: ‎Messages to this chat and calls are now secured with end-to-end encryption.
```
{% endtab %}

{% tab title="Group" %}
```text
[1.1.2019, 12.00.00] John, Jill, Joe: ‎Messages to this group are now secured with end-to-end encryption.
```
{% endtab %}
{% endtabs %}

#### Android

{% tabs %}
{% tab title="Individual" %}
```text
2019-01-01 12:00 - ‎Messages to this chat and calls are now secured with end-to-end encryption.
```
{% endtab %}

{% tab title="Group" %}
```text
2019-01-01 12:00 - ‎Messages to this group are now secured with end-to-end encryption.
```
{% endtab %}
{% endtabs %}

