# Base Stack

Docker compose configuration of containers supporting [Airflow Stack](https://github.com/hughcameron/airflow_stack)

## Traefik Toml

Here's an example of how to set up the `traefik.toml` cofiguration file:

``` toml
logLevel = "DEBUG" # Switch between INFO or DEBUG as needed

[web]
address = ":8080"

defaultEntryPoints = ["http", "https"]

[entryPoints]
  [entryPoints.http]
  address = ":80"
    [entryPoints.http.redirect]
    entryPoint = "https"
  [entryPoints.https]
  address = ":443"
  [entryPoints.https.tls]


[retry]

[docker]
endpoint = "unix:///var/run/docker.sock"
domain = "example.com"
usebindportip = true
watch = true
exposedbydefault = false
# insecureSkipVerify = true

[acme]
email = "myemail@gmail.com"
storage = "acme.json"
entryPoint = "https"
OnHostRule = true
acmeLogging = true
  [acme.dnsChallenge]
  provider = "cloudflare"
  delayBeforeCheck = 0
```

Create a htpasswd on Mac OS using this command in your terminal:

`htpasswd -nb username password`

## Troubleshooting

Be sure to set Universal SSL to Full (strict) otherwise the HTTPS redirect will return a browser error - too many redirects as described [here on Cloudflare docs](https://support.cloudflare.com/hc/en-us/articles/200170516-How-do-I-add-SSL-to-my-site-).

Note that SSL changes may take 24 hours to take effect.# base_stack
