![alt text](https://raw.githubusercontent.com/jonathanvlan/zero/master/Logo-zero.png)


<b>Kernel Security | Integrity Measurement Architecture </b><br>
kernel has as base security the integration of validation with
the following live changes | <br> rootflags=i_version ima_policy=appraise_tcb ima_appraise=fix ima_policy=tcb evm=fix .

<b>Kernel Apparmor Security |</b> Live<br>
One of the main features is the apparmor interaction on live cd that protects all the applications<br>
of the system | apparmor=1 security=apparmor

<b>Kernel Security Parameters | </b><br>
The signed kernel parameters prevent the loading of modified modules, in turn the parameters prevent<br>
different high-profile vulnerabilities such as zombieload and others | <br>
ipv6.disable=1 net.ifnames=0 slab_nomerge slub_debug=FZP mce=0 page_poison=1 pti=on mds=full,nosmt module.sig_enforce=1 components union=overlay vsyscall=none init_on_alloc=1 init_on_free=1 l1tf=full,force<br>
spectre_v2=on spec_store_bypass_disable=seccomp <br>

<b>Kernel Security Parameters |</b> Graph<br>
Kernel parameters intended to protect direct attacks on the graphics card in turn force a safe load |<br>
extra_latent_entropy tsx=off kptr_restrict=2 kexec_loaded_disabled=1 kaslr intel_iommu=on amd_iommu=force<br>
ssbd=force-off tsx_async_abort=off kvm.nx_huge_pages=off kpti=0 nobp=0 deny_new_usb=1

<b>Kernel Encryption Security | </b><br>
Support for system encryption in live mode online security | <br>
persistent=cryptsetup persistence-encryption=luks
