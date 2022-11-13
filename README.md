# libgen
A bash script for downloading comments from disqus.

## Requirements

 - [jq](https://github.com/stedolan/jq)
 - [hgrep](https://github.com/TUVIMEN/hgrep)

## Installation
    install -m 755 disqus /usr/bin

## Supported links formats

    owner
    owner/thread
    @user
    https://disqus.com/home/forum/{owner}/
    http[s]://disqus.com/home/discussion/{owner}/{thread}/
    http[s]://disqus.com/by/{user}/

## Structure

### Discussion

    details.json
    [0-9]+.json

### Forum

    forumfeatures.json
    [0-9]+.json
    {discussion}/

### User

    details.json
    mostactiveforums.json
    favorites-[0-9]+.json
    comments-[0-9]+.json
    threads-[0-9]+.json
    followingchannels-[0-9].json
    badges-[0-9].json

## Usage

    disqus directory [URL]...

The script writes json files downloaded from disqus.

Get everything from user profile to directory x

    disqus x @user
    disqus x https://disqus.com/by/user/

Get everything from discussion to directory x

    disqus x owner/thread
    disqus x https://disqus.com/home/discussion/owner/thread/

Get everyting from forum to directory x

    disqus x owner
    disqus x https://disqus.com/home/forum/owner/
