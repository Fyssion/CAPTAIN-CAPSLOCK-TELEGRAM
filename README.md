# CAPTAIN CAPSLOCK

A Telegram bot that shouts at you when you shout at it.

## How does it operate?

Say something. Say anything. But say it LOUDLY. The cap' will log what you say (for your group chat only) and
shout something random back at you. The more you shout at it, the bigger its repertoire gets.
Duplicate text will not be logged.

## What commands does it have?

Not many.

- /toggle will enable or disable the shout response and logging for you.
- The /togglegroup command will make the shouting auto response opt-in or opt-out for the entire group chat. If it is opt-in,
  users will need to run /toggle before the bot will log their shouts and repeat them.
- If you have permission to delete a message then you can also remove it from the database by replying to it with the
  /remove command.

## What's in a shout?

*Would a scream by any other name still be as loud?*

The algorithm for determining shouts is in [utils/shout.py](https://github.com/bmintz/CAPTAIN-CAPSLOCK/blob/master/utils/shout.py).
All word characters are considered, and if more than half of them are uppercase, the sentence is a shout.
Certain strings are ignored (mostly emoticons). See the utils/shout.py file for more details.

## How do I run this?

You'll need PostgreSQL 11+ and python3.6+.

```
$ createdb captain_capslock
$ psql captain_capslock -f schema.sql
$ cp data/config.example.json data/config.json
$ # edit config.json as needed
$ python3 -m venv .venv
$ source .venv/bin/activate
$ ./bot.py
```

You'll also want to submit the contents of [command_list.txt](/command_list.txt) to The BotFather.

## License

Copyright © 2018–2020 Io Mintz

CAPTAIN CAPSLOCK is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

CAPTAIN CAPSLOCK is distributed in the hope that it will be fun,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with CAPTAIN CAPSLOCK.  If not, see <https://www.gnu.org/licenses/>.
