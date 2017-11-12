# CryptoInscriber

CryptoInscriber - a live cryptocurrency historical trade data poller. Download live historical trade data from any cryptoexchange, be it for machine learning, trading bots, trading strategies, or perhaps minute-level data is just way too expensive.

Outputs to `out/` by default in CSV format. Title will be `{EXCHANGE}_{MARKET}_{ASCTIME}.csv` with columns `Transaction ID, Timestamp (milli), Price, Amount, Side`

Tested on Debian Stretch, and Raspberry Pi 3 Stretch.

## Installation using Virtualenv

```sh
sudo apt install python3 python3-pip
pip3 install virtualenv
python3 -m virtualenv -p python3 env
source env/bin/activate
pip install -r requirements.txt
./cryptoinscriber
```

## Usage

Poll for trade data from Bitstamp on market BTC/USD

`./cryptoinscriber -e bitstamp -m btc/usd`

Poll for trade data from Bitfinex on market BTC/USD, limit to 20 executions per poll

`./cryptoinscriber -e bitfinex -m btc/usd -c '{"limit_trades": 20}'`

Poll for trade data from Quoinex on market BTC/JPY, iterate twice only, limit to 100 executions per poll

`./cryptoinscriber -e bitfinex -m btc/usd -i 2 -c '{"limit": 100}'`

