# Ping without `ping`

When you don't have `ping` nor `nc` nor `telnet` nor `ssh` nor ... installed and you need to test the connection to any host, you can use this

```bash
function pong() {
  host=$1
  port=$2
  (echo >/dev/tcp/${host:-google.com}/${port:-80}) &>/dev/null && echo "open" || echo "close"
}
```

*[source](https://serverfault.com/questions/13780/how-can-i-determine-if-a-machine-is-online-without-using-ping)*