# tzcalc


## Instalation

```
cd /tmp

git clone https://github.com/alvarodeleon/tzcalc

sudo cp tzcalc/tzcalc /usr/sbin/tzcalc

chmod + /usr/sbin/tzcalc
```

## Usage

```bash
tzcalc --local "[timezone],[date] [time]" --query "[timezone_1],[timezone_2]"
```
Example:
```bash
tzcalc -l "America/Montevideo,2022-09-10 15:00" -q "America/New_York.Europe/London,Europe/Rome"
```
Output
```ini
America/New_York.Europe/London
2022-09-10 18:00 America/New_York.Europe/London
2022-09-10 20:00 Europe/Rome
```
Time Zone can be filled in short mode only filling city name, tzcalc will try resolve name of citys and find correct TZ:
```bash
tzcalc -l "Montevideo,2022-09-10 15:00" -q "London,Rome"
```
In case say: "[name] is a invalid TZ" fill complete Time Zone:
```bash
tzcalc -l "America/Montevideo,2022-09-10 15:00" -q "Europe/London,Europe/Rome"
```
If you need calc one date in the future you could fill date and time:
```bash
tzcalc -l "Montevideo,2022-09-10 15:00" -q "London,Rome"
```
If you only fill time, tzcalc assume that date is today:
```bash
tzcalc -l "Montevideo,22:00" -q "New_York,London,Rome"
```
Output:
```ini
2022-09-10 21:00 America/New_York
2022-09-11 02:00 Europe/London
2022-09-11 03:00 Europe/Rome
```