# atlassian-ip-range-fw-cfg
A bash script to generate a firewalld zone xml file from the published Atlassian ip range. To allow access to SSH for Bitbucket Pipelines



## Usage
Main script:
Place [atlassian-ip-range-fw-cfg](Atlassian-ip-range-fw-cfg) in /usr/local/sbin
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
