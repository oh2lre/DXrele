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
In addition to freely flowing DX-infos and solar data:

<@DXrele> FT5ZM       24955.0 10:17Z de LA9FFA   wkd24.960
       AMSTERDAM & ST. PAUL
<@DXrele> OZ7IGY   *  50471.0 08:25Z de OH7TE    PI4 -15 dB Q=38 1052 km        DENMARK

the bot has a few commands. '??' gives the following list.

Send commands to teh bot on this channel or in private:

1) .sh/dx [band] [optionally, number of last spots between 1-7, default is 5]
bands: 160m, 80m, 40m, 30m, 20m, 17m, 15m, 12m, 10m, 6m, 4m, 2m, 70cm, 23cm e.g: .sh/dx 10m 7  or  .sh/dx 2m

<oh2lre> .sh/dx 10m 1
<DXrele> CO6LC       28478.0 12:55Z de CT5GOQ   Thx qso very strong       CUBA

2) .sh [dxcall] List up to 10 last spots for the call, e.g: .sh oh2k

<oh2lre> .sh oh2k
<DXrele> OH2K        14216.5 2014-01-19 12:09Z de ZL3LF    Niko tnx QSO

3) .wx [wx-station] Print wx-station data retrieved from aprs.fi, e.g: .wx oh2kxh

<oh2lre> .wx oh2kxh
<DXrele> OH2KXH @ 2014-02-07 12:51:38Z: wind_speed: 0.9, rain_mn: 0.0,
temp: 0.0, wind_direction: 167, humidity: 96, pressure: 1004.0, rain_24h: 0.0, rain_1h: 0.0, wind_gust: 1.8

4) .aprs [call-ssid] Latest location retrieved from aprs.fi

<oh2lre> .aprs vk2zsz-9
<DXrele> VK2ZSZ-9 @ 2014-02-07 10:43:17Z: in Ernie Beaver Park, State of New South Wales, Australia, cmt: The white Camry.

5) .sol  Print last solar data

<oh2lre> .sol
<DXrele> -> SOL 09Z: SFI=191 R=223 A=9 K=2

6) .wxp [city] Crowdsourced weather forecast, e.g: .wxp monaco

<oh2lre> .wxp verkhoyansk
<DXrele> verkhoyansk, RU @ 2014-02-07T15Z, status: partly cloudy, temp:-43C, humidity:100, wind_dir:90, wind_spd:7

7) .metar [ICAO aeropuerto code] Aviation weather, e.g: .metar katl  World's biggest aeropuerto

<oh2lre> .metar efhk
<DXrele> Helsinki-Vantaa EFHK @ 2014-02-07 13:20Z, EFHK 071320Z
17007KT 0150 R04R/0400N R15/0450N R22L/0450N R04L/0400N FG VV001
00/M00 Q1003 BECMG 0700 VV002 07-02-14 16:17:00
<DXrele> weatherCondition: n/a, elevation: 56, dewPoint: -0,
hectoPascAltimeter: 1003, windSpeed: 07, clouds: n/a, humidity: 100, windDirection: 170, temperature: 0

8) .taf [ICAO aeropuerto code] Aviation weather forecast, e.g: .taf efma  OH0-aeropuerto

<oh2lre> .taf katl
<DXrele> KATL 071356Z 0714/0818 34008KT P6SM SCT200, FM080000 02004KT
P6SM SCT150, FM080400 05003KT P6SM BKN120, FM080700 06003KT P6SM
OVC050, PROB30 0808/0812 -RA BKN035, FM081500 32005KT P6SM BKN100

By the way, if you wanna see DXrele in action, come an join the
channel #ohdxhf @ IRCnet and stay there some time. The channel bot spots
Scandinavian infos.