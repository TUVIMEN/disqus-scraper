# disqus-scraper

A bash script for scraping comments from disqus.

## Requirements

 - [jq](https://github.com/stedolan/jq)

## Installation
    install -m 755 disqus-scraper /usr/bin

## Supported links formats

    owner
    owner/thread
    @user
    http[s]://disqus.com/home/forum/{owner}/
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

    disqus-scraper directory [URL]...

The script writes json files downloaded from disqus-scraper.

Get everything from user profile to directory x

    disqus-scraper x @user
    disqus-scraper x https://disqus.com/by/user/

Get everything from discussion to directory x

    disqus-scraper x owner/thread
    disqus-scraper x https://disqus.com/home/discussion/owner/thread/

Get everyting from forum to directory x

    disqus-scraper x owner
    disqus-scraper x https://disqus.com/home/forum/owner/
