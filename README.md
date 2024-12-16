# Hosting with ansible with cloudflare tunneling.
The tunneling is done with cloudflared and this uses vagrant+ansible to make a virtual machine.

### Requirements
linux host OS, I'm not dealing with window stuff.
A cloudflare domain, you can probably make it with domains from outside cloudflare and just adding them into cloudflare.
Vagrant and ansible.
A pc and internet network.

### Download

download the project by cloning the repo
```
git clone https://github.com/leogamer644/hosting.git
```

### Personalization
 You will have to configure a few things to make it work, first of all. change 
 ```
 shell: cloudflared service install eyJhIjoiMmEzZDgwYWNkNjg0MzUxOTliNDljZjkzODcxZDk5YTkiLCJ0IjoiYWIwMjAzZGItNzI1MC00ZjkyLWFlNzctMGNlNDg0MzI1NDk4IiwicyI6IlpqRXlPV1k1TXpFdE5qWTVNaTAwT1dVMExUbGlNMll0WXpJM1pHVTBZV05oTVdGayJ9
``` 
 in the playbook.yaml file to whatever shows up in your tunnel installation in cloudflare dashboard. If you dont know how to do this, look in this webpage: https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/ .
Dont worry, my tunnel is gonna die in like a week since this commit is done, so dont do stuff pretty please :D.
you will also have to change grafana's domain to one in your tunnels setting. I will show you mine in the folder Vagrant_ansible.
change all the personal stuff like my name in copyright at the bottom to your own.
### Performance
to check performance stats, go to [test images](testimages/readme.md)
### License
this project is under the gnu license if you want to know more, check the [License](LICENSE).
