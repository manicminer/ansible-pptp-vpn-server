# Disposable PPTP VPN Server for Linode

This is awful, but it works. Launches and configures a PPTP VPN server in
a Linode datacenter. For when you want to access geo-blocked services but
they keep trying to blacklist proxy/VPN users. No names mentioned.

### Instructions

1. Install Ansible. `pip install ansible`
2. Type some words into `config.yml`
3. Run the `launch.yml` playbook.
4. Connect a PPTP client and test
5. Repeat from step 3 if you don't get lucky

You may want to adjust the PPP authentication options in `files/pptp-options`
to suit your wacky client.

### Disclaimer

I cobbled this together to use a particular service which happens to be
geo-blocked. The operators are annoying and keep blocking IP addresses
when they smell a VPN or proxy. Which just means I have to re-run this
playbook a couple times.

Please don't use for anything important. This playbook is entertainment-grade
and PPTP is absolutely not secure.

### Usage Example

```shell
ansible-playbook launch.yml -vvv
```

Depending on your local ssh_config, you may need to type 'yes' at the SSH
fingerprint prompt for the initial connection after the instance is launched.

### License

MIT
