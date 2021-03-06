# telegram-entities-decoder

This class decode style entities from Telegram bot messages (bold, italic, etc.) in text with inline entities that duplicate (when possible) the
exact style the message had originally when was sended to the bot.
All this work is necessary because Telegram returns offset and length of the entities in UTF-16 code units that they've been hard to decode correctly in PHP 

## Compatibility
PHP >= 7.0

## Features
- Supports all Telegram parse modes (Markdown, HTML and MarkdownV2). HTML has more entropy but it's easily the best and it's recommended.
- Supports emoji in the text field
- Easy to use

## TODOs
1) Manage Exceptions and wrong inputs
2) Find an easier way to calculate emoji length that not use a regexp or any other way that require to be updated from emoji DB.
3) Right to left writing compatibility

## Example usage
```
$entity_decoder = new EntityDecoder('HTML', 'API_KEY_STRING');
$decoded_text = $entity_decoder->decode($message);
```

## Credits
- Telegram docs: https://core.telegram.org/bots/api#formatting-options
- Inspired By: https://github.com/php-telegram-bot/core/issues/544#issuecomment-564950430
- Emoji detection (with some customizations) from: https://github.com/aaronpk/emoji-detector-php

## Contacts
![Telegram](https://telegram.org/favicon.ico) [@LucaDevelop](https://t.me/LucaDevelop)
