DXrele
======

# DXrele is an irc bot to deliver radio amateur DX-infos, wx, aprs, metar, taf, solar data to your specific irc channel.
# Coding started 01.01.2014. Author Simo Pätäri OH2LRE.
# DXrele is under MIT license. Source location: https://github.com/oh2lre/DXrele
# If you run DXrele on your own, drop me a note. It would be interesting to hear your experience :)
# DX info and solar data source is DXCluster.co.uk
# Aprs and wx data source is aprs.fi
# DXrele is written in Python 2.7.3 and developed on a state-of-the-art Raspberry Pi environment

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
print to your channel. You can change filtering by changing the
if-statement. The present if- statement shows only infos that have a dx
call that starts with German prefix DL. Also, those spots that are
spotted by a German DL are printed. If you want to get JA dx infos too,
the line can be changed to something like:

'if dxcall[:2] == "DL" or call[:2] == "DL" or dxcall[:2] == "JA" or
call[:2] == "JA" or dxcall[:2] == "JR" or call[:2] == "JR":'