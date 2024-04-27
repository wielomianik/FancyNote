### Update pacman database
```
sudo pacman -Syy
```

### Update Arch Linux
```
sudo pacman -Syu
```

### Remove redundant packages (safe)
```
sudo pacman -Rns $(pacman -Qtdq)
```

### Check for current DPI xorg
```
grep "DPI" /var/log/Xorg.0.log
```

### SSH key generation for eg. GitHub or GitLab:
```
ssh-keygen -t rsa -b 4096 -C "example.example@gmail.com"
```

### Compressing files using 7zip
```
7z a -t7z -m0=lzma2 -mx=7 -mfb=32 -md=16m -ms=on -mhe=on -pPASSWORD archive.7z .

7z a -t7z -m0=lzma2 -mx=9 -aoa -mfb=64 -md=32m -ms=on -d=1024m -mhe -pPASSWORD archive.7z .

7z a -t7z -mx=9 -mfb=273 -ms -md=31 -myx=9 -mtm=- -mmt -mmtf -md=1536m -mmf=bt3 -mmc=10000 -mpb=0 -mlc=0 -pPASSWORD archive.7z .
```

### Backup root, Arch Linux, using rsync:
```
sudo rsync -ahSAXH --info=progress2 --delete-excluded --exclude=/dev/* --exclude=/proc/* --exclude=/sys/* --exclude=/tmp/* --exclude=/run/* --exclude=/mnt/* --exclude=/media/* --exclude=/home/* --exclude="lost+found" / /home/user/snapshots/example

--archive, -a            archive mode is -rlptgoD (no -A,-X,-U,-N,-H)
--sparse, -S             turn sequences of nulls into sparse blocks
--xattrs, -X             preserve extended attributes
--acls, -A               preserve ACLs (implies --perms)
--hard-links, -H         preserve hard links
--delete-excluded        also delete excluded files from dest dirs
```

### Check differences in backup:
```
sudo diff -qr --exclude=dev --exclude=proc --exclude=sys --exclude=tmp --exclude=run --exclude=mnt --exclude=media --exclude=home --exclude="lost+found" / /home/user/snapshots/example

-q, --brief              report only when files differ
-r, --recursive          recursively compare any subdirectories found
-x, --exclude=PAT        exclude files that match PAT
```

### Allow SSH, Minecraft server UFW
```
sudo ufw allow from {IP} to any port 22 proto tcp
sudo ufw allow from {IP} to any port 25565 proto tcp
```

### Minecraft Thaumcraft, get rid of FluxRift
```
/kill @e[type=thaumcraft:fluxrift]
```

### Cyberpunk 2077 - Custom proton settings
```
1. gamemoderun mangohud %command% --launcher-skip
2. gamemoderun mangohud %command% --launcher-skip --nogamepad
3. PROTON_LOG=1 DXVK_ASYNC=1 PROTON_ENABLE_NVAPI=1 gamemoderun mangohud %command% --launcher-skip --intro-skip -skipStartScreen
```
