# Flask TinyDB server example

Flask+TinyDBでAPIサーバーをたてるサンプル

## Usage

### GET

`curl`でGETリクエストを投げる方法

```sh
curl http://0.0.0.0:8080/api/load | jq .
```

```sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   265  100   265    0     0  37397      0 --:--:-- --:--:-- --:--:-- 37857
[
  {
    "from": "curl",
    "message": "Hello, world!",
    "title": "post"
  },
  {
    "from": "curl",
    "message": "Hello, world!",
    "title": "post"
  }
]
```

### POST

`curl`でPOSTリクエストを投げる方法

```sh
curl -X POST -H 'Content-Type: application/json' -d '{"title": "post", "message": "Hello, world!", "from": "curl"}' http://0.0.0.0:8080/api/save | jq .
```

```sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   154  100    93  100    61  12355   8104 --:--:-- --:--:-- --:--:-- 13285
{
  "from": "curl",
  "message": "Hello, world!",
  "res": "success",
  "title": "post"
}
```

## What is jq

`jq`はコマンドラインでJSONをきれいに表示してくれるコマンド.  
`curl`でJSONを投げてテストするときに使うけど、利用できない環境であればパイプラインの該当箇所を削除すること.

POSTを投げるテストなんかはPostmanやInsomniaを使うべき.
