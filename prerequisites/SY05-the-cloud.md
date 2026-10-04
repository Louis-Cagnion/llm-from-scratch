# SY05. The cloud

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Systems and performance | 7. Cryptography, security and cloud | IN01, SY04 | none directly (decision taken in L38) |

## Why this module

One laptop GPU is enough to build and validate the whole stack at small scale, but larger runs and real multi-GPU validation need rented machines. Renting GPUs is simple to start and easy to get wrong: a forgotten instance keeps billing, data transfers cost money, and an exposed machine gets attacked within minutes. This module explains the cloud from zero so that the decision taken in L38 is informed and the first rental is safe.

## Objectives

After this module, you can explain how cloud computing works, compare providers and pricing models, compute the cost of a run, access and secure a rented GPU machine, and control spending.

## Competences evaluated

1. Explain the service models (infrastructure, platform, software as a service) and the basic building blocks: virtual machines, GPU instances, block and object storage, virtual networks, regions and zones.
2. Compare the kinds of providers (large general clouds, GPU-specialized clouds, marketplaces of individual machines) and their trade-offs (price, reliability, availability, support).
3. Compare pricing models (on demand, interruptible or spot, reserved) and decide which fits a given run.
4. Compute the cost of a run from its FLOP budget, the hardware's throughput and utilization, its duration, storage and data transfer (including egress), with a safety margin.
5. Create, access and shut down an instance over SSH with keys, and transfer data efficiently.
6. Secure an instance: SSH keys only, firewall rules, no secrets in images, updates, least privilege.
7. Control costs: budgets and alerts, automatic shutdown, checkpointing to survive interruptions, cleaning up storage.
8. Decide, from a budget and a goal, whether renting is worth it, and write a short rental plan.

## Notions, in learning order

1. **What the cloud is**: renting hardware by the hour, virtualization, service models.
2. **Building blocks**: compute instances, GPUs per instance, storage types, networking, regions.
3. **Providers**: the landscape and how to compare offers (GPU model, memory, interconnect, price per hour).
4. **Pricing**: on demand, interruptible, reserved, storage and egress costs, hidden costs.
5. **Estimating a run**: FLOPs, throughput, utilization, hours, total cost, margins.
6. **Access**: SSH keys, connecting, copying data, running long jobs with `tmux`.
7. **Security**: exposed services, firewalls, keys, secrets, updates.
8. **Cost control**: budgets, alerts, automatic shutdown, interruptible instances with checkpoints.
9. **Decision**: when renting is worth it, and a checklist before each rental.

## Practice

- Cost estimates for three hypothetical runs of increasing size, compared across pricing models.
- A rental checklist and a shutdown script written in advance.
- Optionally, once the author decides to: a first rental of a single GPU for one hour, following the checklist, with the actual bill compared with the estimate.

## Evaluation format

One session, about 1 hour 30: cost estimation problems, a security review of a described instance setup, and a written rental plan for a given goal and budget. Pass mark 100 %.

## References

- The official documentation of the providers considered, read at the time of the decision (prices change often).
- MIT, *The Missing Semester of Your CS Education*, lecture on remote machines (free).
