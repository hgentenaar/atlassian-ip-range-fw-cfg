# atlassian-ip-range-fw-cfg
The Atlassian IP range Firewall Config generator is a bash script to generate a firewalld zone XML file from the published Atlassian ip ranges. For allowing access to systems via SSH from Bitbucket Pipelines.
 

## Usage
Main script:
Place [atlassian-ip-range-fw-cfg](atlassian-ip-range-fw-cfg) in /usr/local/sbin
make executable
`sudo chmod +x /usr/local/sbin/atlassian-ip-range-fw-cfg

## systemd timer setup
Place [atlassian-ip-range-fw-cfg.service](systemd/atlassian-ip-range-fw-cfg.service) and [atlassian-ip-range-fw-cfg.timer](systemd/atlassian-ip-range-fw-cfg.timer) in /etc/systemd/system 

### check systemd setup
`sudo systemd-analyze verify /etc/systemd/system/atlassian-ip-range-fw-cfg*`

### Start systemd Timer
`sudo systemctl start atlassian-ip-range-fw-cfg.timer`

## Enable on Boot
`sudo systemctl enable atlassian-ip-range-fw-cfg.timer`
