# linux-shell-alarm

Pre-story: I needed to setup a morning alarm before going to bed.
My phone was discharged and the charger was forgotten at workplace.
The only thing that could help was a computer.
I use TV as a monitor, so I don't have loudspeakers.
Unfortunately my SmartTV is not smart enough and goes to hibernate mode ignoring the 'never sleep' setting.

<br/>

So we have a desktop computer and need to setup an alarm.

<br/>
<hr/>

Tool that schedules tasks in Linux:

    sudo apt-get install at

Script that makes beep-sound:

    me@home-pc:~$ cat alarm.sh
    for i in {1..200}
    do
       beep
       sleep .25
    done

Script invoked by scheduler (just workaround to use bash):

    me@home-pc:-$ cat alarm-runner.sh
    /bin/bash alarm.sh

Setting an alarm:

    at now +8 hours -f ~/alarm-runner.sh

Show all scheduled jobs:

    mey@home-pc:~$ atq
    11      Mon Mar  6 07:20:00 2017 a me

Remove alarm by id:

    at -r 11


<br/>
<hr/>
If beep sound does not work, see [this] (http://askubuntu.com/questions/19906/beep-in-shell-script-not-working) or related threads.




