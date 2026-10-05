---
date: 2026-05-26
tags:
  - informatica
  - linux
  - pubblico

---
# libvirt (virtualization library)
---
Un framework di gestione della virtualizzazione su [[Linux]].

### Perchè esiste?
Perchè gli hypervisor ([[QEMU (Quick EMUlator)]], Xen, VMware) sono troppo grossi e complessi per interagirci agevolmente in molti scenari.

Prendendo come esempio (ma anche altro), avviare una macchina virtuale ti richiederebbe un comando tipo questo:

```
qemu-system-x86_64 \
  -enable-kvm \
  -m 4096 \
  -smp 4 \
  -cpu host \
  -drive file=arch.qcow2,format=qcow2 \
  -cdrom archlinux.iso \
  -boot d \
  -net nic \
  -net user
```

Sono tutti flag che indicano pezzi del computer, uno ad uno. Per QEMU le VM sono processi avviabili in quel modo lì, quindi la prossima volta che dovrai avviarla ri-eseguirai quel comando; i comandi più grossi arrivano a 500 caratteri, che è faticoso da gestire se hai 50 macchine virtuali attorno.

Qui interviene libvirt, che funzionando da strato di astrazione ti dà un'interfaccia unificata per: creare VM, avviarle, spegnerle, configurare reti, gestire dischi, snapshot, permessi, migrazioni etc.

Libvirtd ti permetterebbe di avviare quella vm con un `virsh start arch-vm` nella sua versione CLI.

È comodo standardizzare così, ed è da qui che nascono strumenti dedicati come API, libvirtd (daemon), file XML di configurazione, virsh (CLI) e GUI varie (virt-manager).

---
[[KVM (Kernel-based Virtual Machine)]]