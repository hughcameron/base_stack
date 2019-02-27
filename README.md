# Base Stack

Docker compose configuration of containers supporting [Airflow Stack](https://github.com/hughcameron/airflow_stack)

A useful guide on creating encrypted htpasswd strings provided [in the Portainer docs](https://portainer.readthedocs.io/en/stable/configuration.html#admin-password).

## Troubleshooting

Be sure to set Universal SSL to Full (strict) otherwise the HTTPS redirect will return a browser error - too many redirects as described [here on Cloudflare docs](https://support.cloudflare.com/hc/en-us/articles/200170516-How-do-I-add-SSL-to-my-site-).

Note that SSL changes may take 24 hours to take effect.# base_stack
