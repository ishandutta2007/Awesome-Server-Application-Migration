# Awesome-Server-Application-Migration

## Top Server & Application Migration Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Workload Migration, Disaster Recovery & Open-Source Data Mobility*  

**Last updated: October 2026**



This repository tracks notable **commercial server and application migration platforms** and **open-source projects** that move workloads between physical servers, virtual machines, and cloud environments. These tools range from continuous replication engines to agentless discovery and cutover orchestration.



**Examples** include AWS Application Migration Service, Azure Site Recovery, Google Cloud Migrate to Virtual Machines, Carbonite Migrate, Zerto, Veeam, CloudEndure, PlateSpin Migrate, Cohesity, and Commvault (the category leaders).



**Open-source emphasis**: Server and application migration is anchored by **virt-v2v** as the foundational V2V conversion tool, **Coriolis** for cloud migration as a service, **h2kvm** for VDDK-free VMware migration, **Migration Manager** for VMware-to-Incus, and **hyper2kvm** for enterprise-scale migration with Kubernetes operator. **Reloader** and **Transiva** handle disk export. This section is heavily expanded.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[AWS Application Migration Service](https://aws.amazon.com/application-migration-service/)**  

  **AWS's primary migration service** — lift-and-shift physical, virtual, or cloud servers to AWS . **Continuous block-level replication** with minimal downtime . **The reference for AWS migrations** . **Best for AWS cloud migration** .



- **[Azure Site Recovery](https://azure.microsoft.com/en-us/products/site-recovery/)**  

  **Microsoft's disaster recovery and migration service** — replicate and migrate VMs to Azure . **Best for Azure migrations** .



- **[Google Cloud Migrate to Virtual Machines](https://cloud.google.com/migrate/virtual-machines)**  

  **Google's VM migration service** — migrate from VMware, AWS, and Azure to GCP . **Best for GCP migrations** .



- **[Carbonite Migrate](https://www.carbonite.com/migrate/)**  

  **Real-time replication and migration** — minimal downtime cutover . **Best for heterogeneous migrations** .



- **[Zerto](https://www.zerto.com/)**  

  **The enterprise standard for IT resilience and migration** — continuous replication and automated failover . **Best for enterprise DR and migration** .



- **[Veeam](https://www.veeam.com/)**  

  **Backup and replication platform with migration capabilities** . **Best for VMware and Hyper-V migrations** .



- **[CloudEndure](https://www.cloudendure.com/)**  

  **AWS's disaster recovery and migration service** — continuous block-level replication . **Best for live migration** .



- **[PlateSpin Migrate](https://www.microfocus.com/en-us/products/platespin-migrate/overview)**  

  **Micro Focus's workload migration** — physical, virtual, and cloud migrations . **Best for heterogeneous environments** .



- **[Cohesity](https://www.cohesity.com/)**  

  **Data management with migration capabilities** — backup, recovery, and cloud migration . **Best for data-centric migration** .



- **[Commvault](https://www.commvault.com/)**  

  **Enterprise data management with migration** — backup, recovery, and cloud migration . **Best for enterprise data management** .



## Open-Source GitHub Projects



### Core V2V & Migration Tools



- **[virt-v2v](https://github.com/libguestfs/virt-v2v)**  

  **The foundational open-source V2V conversion tool**, GPL-2.0 licensed . **Converts guests from VMware, Xen, Hyper-V, and other hypervisors to run on KVM** . **Modifies guests to make them bootable on KVM and installs virtio drivers** for performance . **Continuously developed since 2007** — the reference implementation for guest conversion . **Companion tool virt-p2v** virtualizes physical machines . **Trade-off**: VDDK public downloads ended September 2026 — migration tools must use alternative transport paths . **Best for direct V2V conversion to KVM** .



- **[h2kvm](https://github.com/zyvorai/h2kvm)**  

  **Any hypervisor → KVM migration toolchain**, open-source . **No VDDK dependency** — disks leave through vSphere API and NFS, then convert offline . **Offline guest fixes for VirtIO, GRUB, and Windows bootloader before power-on** . **Includes GuestKit** for disk inspection before boot, **Zorvia** for KubeVirt VM management, **Zeus OS** for visual infrastructure, and **Machina** as libvirt control plane . **PyPI package**: `pip install "h2kvm==1.2.1"` . **Best for VDDK-free VMware migration** .



- **[Coriolis](https://github.com/cloudbase/coriolis)**  

  **Cloud Migration as a Service platform**, Apache-2.0 licensed . **Migrates VMs, templates, storage, and networking between clouds** — VMware vSphere, SCVMM, Azure, AWS, OpenStack, and GCP . **Automatically injects drivers and tools** — cloud-init/cloudbase-init for OpenStack, LIS kernel modules for Hyper-V and Azure . **Uses Oslo libraries with OpenStack-style architecture** — stateless microservices, queues, and scalability . **API-driven** with Postman collection available . **Best for cloud-to-cloud and on-prem-to-cloud migrations** .



- **[Migration Manager (FuturFusion)](https://github.com/FuturFusion/migration-manager)**  

  **Modern instance migration tool for VMware → Incus**, Apache-2.0 licensed . **Runs as a service with REST API, CLI, and web interface** . **Add sources (vCenter/ESXi) and targets (Incus clusters), query instances, override VM sizing, define batches, and track migrations in background** . **v0.6.15** (August 2026) with active development . **Best for VMware-to-Incus migrations** .



- **[hyper2kvm](https://github.com/ssahani/hyper2kvm)**  

  **Enterprise-grade VM migration toolkit**, LGPL-3.0 licensed . **Production-ready v1.0.0** with 96.8% success rate and 2-3x faster than traditional tools . **Kubernetes Operator (v1.6.0)** with Helm chart, admission webhooks, and 20+ Prometheus metrics . **480+ VMCraft API methods** with 90%+ test coverage . **Includes GuestKit** — pure-Rust VM disk inspection with AI-powered diagnostics for pre-migration validation . **Best for enterprise-scale migration with Kubernetes orchestration** .



### Disk Export & Conversion



- **[Reloader](https://github.com/farodin/reloader)**  

  **NFC-based VMware disk export without VDDK**, open-source . **Exports VMDK disks from ESXi hosts** . **Best for VDDK-free disk export** .



- **[Transiva](https://github.com/marazmiki/transiva)**  

  **NFC-based VMware disk export**, open-source . **Alternative to VDDK for disk transfer** . **Best for VDDK-free migration** .



- **[GuestKit](https://github.com/ssahani/guestkit)**  

  **Pure-Rust VM disk inspection with AI-powered diagnostics**, open-source . **Inspects disks before migration** — detects OS, drivers, and boot issues . **Best for pre-migration validation** .



- **[libguestfs](https://github.com/libguestfs/libguestfs)**  

  **Library for accessing and modifying VM disk images**, GPL-2.0 licensed . **The foundation for virt-v2v and other migration tools** . **Best for disk image manipulation** .



### Cloud Migration Frameworks



- **[OpenNebula OneSwap](https://github.com/OpenNebula/one-swap)**  

  **Migrate VMware workloads to OpenNebula/KVM**, open-source . **In-place conversion on datastore** — no local copy, terabyte disks work on workers with small local storage . **Runs virt-v2v-in-place to install virtio drivers and fix initramfs/bootloader** . **Best for OpenNebula migrations** .



- **[EuroMigrator Engine](https://hub.docker.com/r/euromigrator/engine)**  

  **Enterprise cloud migration to sovereign EU providers**, open-source . **47 cloud services across 7 providers** — AWS, Azure, GCP to European alternatives . **AI-powered migration planning and risk assessment** . **GDPR compliant** with encryption at rest and transit . **Best for EU data sovereignty migrations** .



- **[xmigrate](https://hub.docker.com/r/xmigrate/xmigrate)**  

  **Open-source infrastructure migration tool**, CC BY-NC-ND 4.0 licensed . **DC to DC, DC to cloud, cloud to DC, and cloud to cloud** VM migration . **Agentless discovery and migration** to AWS, GCP, and Azure . **Best for simple cloud migrations** .



### Live Migration & Hypervisor



- **[Libvirt/QEMU Live Migration](https://ubuntu.com/server/docs/explanation/virtualisation/live-migration/)**  

  **The foundational open-source live migration capability** . **QEMU streams VM memory and CPU state; libvirt coordinates** the handoff between hosts . **Versioned machine types and CPU baselines** enable migration across heterogeneous infrastructure . **Best for KVM-to-KVM live migration** .



- **[oVirt](https://github.com/oVirt/ovirt-engine)** — Open-source virtualization management with migration capabilities  .

- **[Proxmox VE](https://github.com/proxmox/pve-manager)** — Built-in migration for VMs and containers .

- **[Harvester](https://github.com/harvester/harvester)** — HCI with VM migration support  .

- **[OpenStack Nova](https://github.com/openstack/nova)** — Live migration with parallel memory transfer (Gazpacho 2026.1) and vTPM support  .



### Additional Strong Open-Source Options



- **virt-p2v** — Companion tool for physical-to-virtual migration .

- **virt-v2v-in-place** — In-place conversion for existing VMs .

- **KubeVirt** — VM management on Kubernetes with migration capabilities .

- **oVirt** — Open-source virtualization management .

- **OpenStack** — Cloud infrastructure with migration .

- **CloudStack** — Cloud platform with migration .

- **Terraform** — Infrastructure as Code for target environment provisioning .

- **Ansible** — Configuration management for post-migration setup .



**Frameworks for building custom server and application migration solutions**: Combine **virt-v2v** as the foundational conversion engine . Use **h2kvm** for VDDK-free migration with offline guest repair . Deploy **Coriolis** for cloud-to-cloud and on-prem-to-cloud migrations with driver injection . Choose **Migration Manager** for VMware-to-Incus with modern web interface . Use **hyper2kvm** for enterprise-scale migration with Kubernetes operator . Integrate **GuestKit** for pre-migration disk inspection . Note that true enterprise migration with continuous replication, automated failover, and vendor-supported SLAs (Zerto, Veeam, AWS MGN) remains primarily commercial territory; open-source stacks provide strong conversion, cloud migration, and live migration foundations that require integration for complete enterprise deployment.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Server and application migration involves moving critical workloads and data. **Test migrations in isolated environments first** — driver issues, bootloader problems, and driver signing failures can cause boot loops .

- **VDDK public downloads ended September 2026** — tools relying on VMware's Virtual Disk Development Kit must use alternative transport paths (NFS, HTTPS) .

- **Windows Server 2025 migration requires specific configurations** — UEFI/q35 machine type and CPU passthrough are required for successful boot . Virtio driver signing issues can cause reboot loops .

- **Open-source migration tools require operational expertise** — disk conversion, driver injection, and cutover orchestration are complex. Plan for testing and rollback capabilities.

- The open-source ecosystem provides strong conversion, cloud migration, and live migration foundations, but **continuous replication, automated failover, and vendor-supported SLAs** remain primarily commercial offerings.



---



**Made for infrastructure architects, cloud engineers, and organizations seeking migration sovereignty.**  

Let's make server and application migration more open, transparent, and accessible.
