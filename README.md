DXrele
======

DXrele is an irc bot to deliver radio amateur DX-infos, wx, aprs,
metar, taf, solar data to your specific irc channel. Coding was
started on 01.01.2014. Author is Simo Pätäri OH2LRE. DXrele is under
MIT license. Source location: https://github.com/oh2lre/DXrele. If you
run DXrele, please drop me a note. It would be interesting to hear
your experience :) DX info and solar data source is DXCluster.co.uk.
Aprs and wx data source is aprs.fi. DXrele is written in Python 2.7.3
and developed on a state-of-the-art Raspberry Pi environment.

    A. Setup instructions
Open DXrele.py, and fill your personal values to variables on
lines 21-30. Go and create your own active user account at
http://www.geonames.org/login, own API key at http://aprs.fi/page/api,
and you need to know your irc server address, port, and you need to
decide your bot nick and bot channel. 

    B. Run DXrele
On a command line type 'python DXrele.py'
If everything goes okay, you should see your bot on your IRC channel and
you can start interacting with it by printing the command list with '??'

    C. Fine tuning DX-info filtering
DXrele.py line 143 has if-statement that defines which DX-infos are
printed to your channel. You can change filtering by changing the
if-statement. The present if-statement shows only infos that have a dx
call that starts with the German prefix DL. Also, those spots that are
spotted by a German DL are printed. If you want to get JA dx infos too,
the line can be changed to something like:

'if dxcall[:2] == "DL" or call[:2] == "DL" or dxcall[:2] == "JA" or
call[:2] == "JA" or dxcall[:2] == "JR" or call[:2] == "JR":'

    D. Commands
In addition to freely flowing DX-infos and solar data, the bot has a few commands. '??' gives the following list.

Send commands to teh bot on this channel or in private:
1) .sh/dx [band] [optionally, number of last spots between 1-7, default is 5]
bands: 160m, 80m, 40m, 30m, 20m, 17m, 15m, 12m, 10m, 6m, 4m, 2m, 70cm, 23cm e.g: .sh/dx 10m 7  or  .sh/dx 2m
2) .sh [dxcall] List up to 10 last spots for the call, e.g: .sh oh2k
3) .wx [wx-station] Print wx-station data retrieved from aprs.fi, e.g: .wx oh2kxh
4) .aprs [call-ssid] Latest location retrieved from aprs.fi  5) .sol  Print lasts solar data
6) .wxp [city] Crowdsourced weather forecast, e.g: .wxp monaco
7) .metar [ICAO aeropuerto code] Aviation weather, e.g: .metar katl  World's biggest aeropuerto
8) .taf [ICAO aeropuerto code] Aviation weather forecast, e.g: .taf efma  OH0-aeropuerto


By the way, if you wanna see DXrele in action, come an join the
channel #ohdxhf @ IRCnet and stay there some time. The channel bot
spots Scandinavian infos.
