csminer v0.1.0 (OSX version)

SYNOPSIS

csminer from https://cryptonote.social is an easy-to-use CPU miner for Monero intended to provide
"set it and forget it" mining for your existing laptop and desktop machines. By default, csminer
mines with a single thread, and only when your screen is locked and on AC power. It can be
configured to always mine or mine with more threads using the options described below.


USAGE

./csminer [OPTION]...

All arguments are optional:
  -user <string>
        your pool username from https://cryptonote.social/xmr (default "donate-getmonero-org")
  -saver <bool>
        mine only when screen is locked (default true). csminer polls the OSX lock screen
        state every 10 seconds and should activate the miner shortly after the screen locks.
  -exclude <string>
        pause mining during the specified hours. Format is XX-YY where XX and YY are hours of
        the day designated in 24 hour time. For example, -exclude=11-16 will pause mining betwen
        11:00am and 4:00pm. This can be used, for example, to pause mining during times of high
        machine usage or high electricity rates.
  -threads <int>
        number of threads (default 1)
  -rigid <string>
        your rig id (default "csminer")
  -tls <bool>
        whether to use TLS when connecting to the pool (default false)
  -start_diff <int>
        starting difficulty value for the pool

Monitor your miner progress at: https://cryptonote.social/xmr, or type <p> + <enter> to display
pool stats in the command shell.

Tips:

In Mac Energy Settings, click Power Adapter, and if present, enable the option "Prevent computer
from sleeping automatically when the display is off".

For best performance, if csminer reports it's unable to allocate hugepages, try restarting your
machine and starting csminer before running anything else.

If you don't specify a username, csminer will mine on behalf of the Monero project
(https://donate.getmonero.org) with earnings going directly to its wallet:

888tNkZrPN6JsEgekjMnABU4TBzc2Dt29EPAvkRxbANsAnjyPbb3iQ1YBRk1UXcdRsiKc9dhwMVgN5S9cQUiyoogDavup3H


ADDITIONAL DETAILS

Usernames

If you don't already have a username established with the pool, you can create one by simply
specifying -user=your-wallet-id.your-chosen-username, e.g.:

./csminer -user=888tNkZrPN6JsEgekjMnABU4TBzc2Dt29EPAvkRxbANsAnjyPbb3iQ1YBRk1UXcdRsiKc9dhwMVgN5S9cQUiyoogDavup3H.donate-monero-org

Once you've submitted at least one share, the wallet address is permanently associated with the
username and you can login with the username alone, e.g.:

./csminer -user=get-monero-org

Implementation

csminer utilizes the RandomX implementation from https://github.com/tevador/RandomX and will
perform similarly to other mining software based on this library such as xmrig. 

Feedback & Bug Reports

Send to: <cryptonote.social@gmail.com>
