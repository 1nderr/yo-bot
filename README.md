# yo-bot

This is a Discord bot written in Python that lets the boys vote on whether they are getting on Discord. It
posts a poll in the same channel at the same time every day and reads the reactions back out.

![](https://github.com/1nderr/yo-bot/blob/main/demo.png?raw=true)

## Features

### The Daily Poll

Every day at the hour and minute you set, the bot posts a "Yo or No?" embed in the channel you set and adds
the yo and no reactions to it, so all anyone has to do is click.

### Reading the Votes

As people react, the bot posts each vote in the channel as its own message, so you can see who is in and who
is out without opening the reaction list. It stops watching once three different people have voted, or after
an hour and a half, whichever happens first.

Note: The three vote cutoff is hardcoded in `schedule_cog.py`, since it was written for a group of that
size. Change it there if there are more of you.

## Env

The following is required in a `.env` file:

- `TOKEN`: the bot's secret token.
- `TZ_IDENTIFIER`: timezone identifier string. Ex: `America/New_York`.
- `SCHEDULE_HOUR`: the hour at which the message will be sent.
- `SCHEDULE_MINUTE`: the minute at which the message will be sent.
- `CHANNEL_ID`: the id of the channel where the message will be sent
- `YO_EMOJI`: the "yo" emoji using Discord's format. Ex: `<:yo:689957806891204660>`
- `NO_EMOJI`: the "no" emoji using Discord's format. Ex: `<:no:483957824851202621>`

## Dependencies

- `python 3.12`

### Python Dependencies

- `discord.py`
- `python-dotenv`

To use the `requirements.txt` file, just run `pip3 install -r requirements.txt`.

## Build

`docker build -t yobot .`

## Run

`docker run --rm -d yobot`
