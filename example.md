    Download virtualbox https://www.virtualbox.org/wiki/Downloads
    Install virtualbox
    Create new vm with specs: RAM 8GB DISK 50GB CPU 4 CORE NETWORK ADAPTERS: network adapter 1 - enabled host-only network adapter 2 - enabled bridged
    Download proxmox iso https://www.proxmox.com/en/downloads/proxmox-virtual-environment/iso
    In network adapter 2 in mixed mode enable all
    Attach iso file to virtual CD drive
    Start VM
    install with these details: Hostname - pve[X].local ( kai [X] = darbo vietos nr., pvz. 07) root pass - Jsysadm0
    After installation remove iso from virtual CD drive
    Login to proxmox in your host webbroser with url same as shown in proxmox vm
    In datacenter -> pve[x] in repositories tab disable enterprise repos and add no-subscription
    In network tab copy gateway IP from vmbr0
    On vmbr0 click edit and remove gateway
    Create new network bridge with copied gateway IP bridge port nic2 IPv4 ip similar to gateway ip just last 3 digits different example 100 and add /24 to end
    Click apply configuration
    In datacenter -> pve[x] -> local (pve[x]) -> CT templates click on templates and download latest ubuntu template
    Click Create CT on top of screen with specs: CPU - 1 core RAM - 2 GB DISK - 5GB ADD public key (windows host) root pass - jsysadm
    click on new container (id 100) and click console
    run apt install neofetch
