# Ansible role rss2irc

Ansible role for configuration and deployment of [rss2irc].

## Requirements

This role does install some packages like `git` and `python3`.

## Role variables

See `defaults/main.yml`.

## Dependencies

There are no extra dependencies as far as Ansible goes. However, note that you
must setup cron jobs by yourself eg. use another Ansible role.

Example cron job setup with [ansible-cron]:

```yaml
---
cron_tasks:
  - name: rss2irc
    cron_file: rss2irc
    day: '*'
    hour: '*'
    job: '/opt/rss2irc/scripts/rss2irc.sh 1>/dev/null 2>&1'
    minute: '*/10'
    month: '*'
    state: present
    user: root
    weekday: '*'
```

## License

MIT

[ansible-cron]: https://github.com/weareinteractive/ansible-cron
[rss2irc]: https://github.com/zstyblik/rss2irc
