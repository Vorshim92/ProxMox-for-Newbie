# <div align="center">**ProxMox for Newbie**</div>

Una semplice guida (ITA-ENG) per nabbazzi come me! giusto per tenere  a portata comandi e nozioni! se ho scritto cazzate sentitevi liberi di commentare e aprire issue a gogo e anche di insultarmi!

![logo](./images/proxmoxlogo.webp)

# SOMMARIO
**CONTENUTI**

- [**SETUP INIZIALE - BIOS**](#setupbios)


## SETUP/BIOS:
prima di partire con l'installazione vera e propria di PROXMOX assicuriamoci di mettere l'impostazione UEFI nel BIOS:

> [!IMPORTANT]
> è assolutamente importante DISABILITARE  dal BIOS anche l'impostazione SECURE BOOT e CSM/Legacy

alcune immagini esempio di queste impostazioni (potrebbero variare in base alla scheda madre in quanto pozione ma tendenzialmente si troveranno sulla scheda BOOT)
<details>
  <summary>IMMAGINI</summary>
 <img src="./images/CSM.png" alt="CSM" width=50% height="50%">
 <img src="./images/UEFI.jpg" alt="UEFI" width=50% height="50%">
 <img src="./images/SecureBoot.jpg" alt="SecureBoot" width=60% height="60%"></details>


Fatto questo il nostro sistema ProxMox verrà installato senza problemi in modalità UEFI.

Cominciamo quindi inserendo il pennino usb precedentemente formattato (io uso Rufus per formattarlo e metterci sopra la ISO di Proxmox)
e avviamolo, seguiranno una serie di immagini esempio del processo di installazione:
<details>
  <summary>IMMAGINI</summary>
 <img src="./images/setup/1.png" alt="CSM" width=50% height="50%">
 <img src="./images/setup/2.png" alt="UEFI" width=50% height="50%">
 <img src="./images/setup/3.png" alt="SecureBoot" width=50% height="50%">
 <img src="./images/setup/4.png" alt="CSM" width=50% height="50%">
 <img src="./images/setup/5.png" alt="UEFI" width=50% height="50%"></details>

 dopo il riavvio vi ritroverete su una schermata nera con il login, a noi interesserà soltanto segnarci l'indirizzo IP per poter entrare nella WebUI da un altro pc in rete tramite browser:
 <img src="./images/setup/IP-login.png" alt="SecureBoot" width=50% height="50%">








Volendo fare un check per assicurarci che sia effettivamente così potremmo dare questo comando dalla shell:


```
efibootmgr -v
```


se l'output del comando darà una cosa del genere allora il bootloader (GRUB) starà utilizando la modalità UEFI:
> Boot0005* proxmox       [...] File(\EFI\proxmox\grubx64.efi)

se nell'output uscirà invece "systemd-boot" allora sarà SystemD-Boot il bootloader e non GRUB (ma sempre in UEFI mode) .
> Boot0006* Linux Boot Manager    [...] File(\EFI\systemd\systemd-bootx64.efi)

> [!NOTE]
> Una cosa che mi ha fatto tribolare inizialmente! Il fatto che vedrete GRUB come bootloader non vorrà dire che il sistema sarà in modalità LEGACY!!
Per distinguere quale dei 2 bootloader è utilizzato basterà mandare il comando di prima e leggere l'output ma già dalla parte estetica sarà possibile riconoscerli.
GRUB è GRUB, schermata blu con la scritta GRUB in alto (vedi foto)
> <img src="./images/GRUB.png" alt="GRUB" width=50% height="50%">
> Systemd-Boot è riconoscibile da una schermata nera molto semplice con 1 o 2 righe al centro selezionabili. (vedi foto)
> <img src="./images/systemdboot.png" alt="SystemdBoot" width=50% height="50%">














<details>
  <summary>testo</summary>
ex:
# Titolo H1
## Titolo H2
### Titolo H3
#### Titolo H4
##### Titolo H5
align="left" or "right"</details>

> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.

<p align="center">
  <img eccecc>
</p>

> efibootmgr -v
> *efibootmgr -v*
> **efibootmgr -v**
`efibootmgr -v`
<kbd>efibootmgr -v</kbd>