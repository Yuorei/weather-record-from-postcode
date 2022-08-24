# weather-record-from-postcode
**概要**

このプログラムはcsvファイルに記入されている郵便番号を読み込んでそこの地域の天気と気温を日付時刻と場所も含めて24時間ごとにcsvファイルに出力します

**作った動機**

自分が選んだ毎日の各地の天気の情報を記録として残せて検索も可能なものがあると便利だと思ったから

**使い方**

postcode.csvに記録したい場所の郵便番号(ハイフンなし)を一行の一つづつ記入します
これを用意した状態でmain.goを実行するとtime_place_weather_temperature.csvに24時間ごとに結果が得られます

**プログラムについて**

まずcsvから郵便番号を読み込みます
HeartRails Geo APIを利用して郵便番号から緯度(latitude)と経度(longitude)をjsonから読み取ります
この値を利用してOpenWeatherAPIから正確な位置の気象情報を取得します
データをcsvファイルに書き込みます
日付時刻はtime.Now()からもってきています
24時間待機して再び最初に戻ります

出典:「位置参照情報」(国土交通省)の加工情報・「HeartRails Geo API」(HeartRails Inc.)
