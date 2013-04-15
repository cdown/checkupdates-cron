`checkupdates-cron` is a tiny wrapper around the Arch Linux `checkupdates`
script that will only print output if the updates available are different than
the last time they were checked. This is useful if you run checkupdates as part
of a cronjob, as it allows e-mails only to be sent when the available packages
change, and not every time (which results in a lot of e-mails to sift through).

# Setting up a cronjob

Use something like this in `/etc/cron.d`:

    PATH=/usr/bin
    */15 * * * * nobody checkupdates-cron
