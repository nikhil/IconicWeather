# IconicWeather

A script used with `i3blocks` that monitors weather from Accuweather and displays the weather on your bar. <br>
Modified from the script found <a href="https://gist.github.com/cirrusUK/fa9e6a7551e511331020">here.</a> <br>
Scans the `WeatherText` and displays the `temperature` with its corresponding `Font Awesome` icon. <br>
Changed the perl script to modify the output: <br>
```
'use utf8; 
if (/Currently/) {chomp;/\<title\>Currently: (.*)?\<\/title\>/; 
my @values=split(":",$1); 
if( $values[0] eq "Sunny" || $values[0] eq "Mostly Sunny" || $values[0] eq "Partly Sunny" || $values[0] eq "Intermittent Clouds" || $values[0] eq "Hazy Sunshine" || $values[0] eq "Hazy Sunshine" || $values[0] eq "Hot") 
{my $sun = "";binmode(STDOUT, ":utf8");print "$sun";}
if( $values[0] eq "Mostly Cloudy" || $values[0] eq "Cloudy" || $values[0] eq "Dreary (Overcast)" || $values[0] eq "Fog")
{my $cloud = "";binmode(STDOUT, ":utf8");print "$cloud";}
if( $values[0] eq "Showers" || $values[0] eq "Mostly Cloudy w/ Showers" || $values[0] eq "Partly Sunny w/ Showers" || $values[0] eq "T-Storms"|| $values[0] eq "Mostly Cloudy w/ T-Storms"|| $values[0] eq "Partly Sunny w/ T-Storms"|| $values[0] eq "Rain")
{my $rain = "";binmode(STDOUT, ":utf8");print "$rain";}
if( $values[0] eq "Windy"){my $wind = "";binmode(STDOUT, ":utf8");print "$wind";} 
if($values[0] eq "Flurries" || $values[0] eq "Mostly Cloudy w/ Flurries" || $values[0] eq "Partly Sunny w/ Flurries"|| $values[0] eq "Snow"|| $values[0] eq "Mostly Cloudy w/ Snow"|| $values[0] eq "Ice"|| $values[0] eq "Sleet"|| $values[0] eq "Freezing Rain"|| $values[0] eq "Rain and Snow"|| $values[0] eq "Cold")
{my $snow = "";binmode(STDOUT, ":utf8");print "$rain";}
if($values[0] eq "Clear" || $values[0] eq "Mostly Clear" || $values[0] eq "Partly Cloudy"|| $values[0] eq "Intermittent Clouds"|| $values[0] eq "Hazy Moonlight"|| $values[0] eq "Mostly Cloudy"|| $values[0] eq "Partly Cloudy w/ Showers"|| $values[0] eq "Mostly Cloudy w/ Showers"|| $values[0] eq "Partly Cloudy w/ T-Storms"|| $values[0] eq "Mostly Cloudy w/ Flurries" || $values[0] eq "Mostly Cloudy w/ Snow")
{my $night = "";binmode(STDOUT, ":utf8");print "$night";}
print"$values[1]"; }'
```
Here is a preview: <br>
<img src="i3bar.png">
