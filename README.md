# dohot-service
DNS Over HTTPS over Tor for Anonymized DNS with adblocking, with [Pi-Hole](https://github.com/pi-hole/pi-hole) and [Cloudflared](https://github.com/cloudflare/cloudflared)

Cribbed from [Alec Muffett's DoHoT](https://github.com/alecmuffett/dohot).

This doesn't currently have the "load-balancing" aspect of the DNSCrypt-proxy service, but I have included a `Dockerfile` for `dnscrypt-proxy` and will look to include a section in the `docker-compose.yml` to support this too.
