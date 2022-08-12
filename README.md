# ssh-notes

`ssh-notes` is a basic notes system allowing you to view and edit a set of notes on a remote ssh server.
NOTE: This is not a secure system, only people who are allowed full ssh access to the remote server should be allowed to use this system.


## Prerequisites

All devices need to be running on Linux (or WSL)

### Server

- [Bat](https://github.com/sharkdp/bat) v0.18.0 or higher
- OpenSSH server
- `watch` command needs to be available (I doubt this is a problem for anyone though)

### Client

- OpenSSH client (any recent version should be fine)

## Installation

Install the `notes-view` and `notes-edit` commands by copying the files into a directory in your PATH.
Add the ssh destination (user@hostname) into the `~/.ssh-notes/destination` file (you will need to create this directory if it doesn't exist)

Make sure that the `$EDITOR` environment variable on the server is set to your preferred editor. This will be used in the `notes-edit` command.

## Usage

### notes-view

This command will essentially watch the `~/.ssh-notes/notes.md` file on the remote server, updating every 2 seconds. Any command line arguments will be passed through to `bat`, useful if the rendering looks weird on your terminal and you want to override the theme or style

### notes-edit

This command will allow you to edit the `~/.ssh-notes/notes.md` file on the remote server.

(c) 2022 Yamboy
