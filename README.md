# Cloud Hosting Explained: What You're Paying For, When a VPS Is the Better Buy, and Which Vultr Plan Fits (Full Pricing Table)

Cloud hosting runs your site or application across a network of virtual servers instead of a single machine, and meters what you reserve by the hour. One server hitting its limit doesn't take you offline, and adding capacity next month doesn't mean migrating to a new plan.

Vultr is one of the lower-cost places to buy that model. Cloud Compute starts at $2.50/month, the 1 vCPU / 2 GB NVMe tier is $12/month, dedicated-vCPU instances start around $28/month, and new accounts can pick up a $300 promotional credit. Below: how the billing actually behaves, where a plain VPS still does the job for less, and which terms decide whether the credit is worth anything to you.

> **Quick picks**
> - App or API with real users: Cloud Compute High Performance, 1 vCPU / 2 GB / NVMe, **$12/month**.
> - Static site, staging box, VPN, cron jobs: Cloud Compute Regular Performance, **from $2.50/month**.
> - Database or steady CPU load: Optimized Cloud Compute with dedicated vCPU, **from about $28/month**.
>
> 👉 [Check current Vultr pricing and deploy a plan](https://bit.ly/VuLtr)

## Vultr's compute plans, family by family

Vultr doesn't sell one ladder of plans. It sells several hardware families, and each has its own size ladder, so the cheapest option in a family tells you less than the shape of the family. Prices below are monthly, metered hourly, and shift slightly by region.

| Plan family | Entry configuration | Price | Who it fits | Get started |
| --- | --- | --- | --- | --- |
| Cloud Compute, Regular Performance | Shared vCPU, standard SSD | from $2.50/mo | Static sites, staging, DNS and VPN boxes | [Deploy Regular Performance](https://bit.ly/VuLtr) |
| Cloud Compute, High Performance | 1 vCPU, 2 GB RAM, NVMe | $12/mo | Production app servers, small SaaS, container hosts | [Deploy High Performance](https://bit.ly/VuLtr) |
| Cloud Compute, High Frequency | High-clock Xeon cores, NVMe | from $6/mo | Latency-sensitive APIs, job queues, CI runners | [Deploy High Frequency](https://bit.ly/VuLtr) |
| Optimized Cloud Compute | Dedicated vCPU; general-purpose, compute-, memory- and storage-optimized shapes | from ~$28/mo | Databases, busy APIs, anything with sustained CPU | [Deploy Optimized Cloud Compute](https://bit.ly/VuLtr) |
| Cloud GPU | GPU-backed instances | from ~$90/mo | Inference, model training, rendering | [Deploy a GPU instance](https://bit.ly/VuLtr) |
| Bare Metal | Whole physical server, no hypervisor layer | from ~$120/mo | Licensing constraints, heavy I/O, dedicated hardware | [Deploy Bare Metal](https://bit.ly/VuLtr) |

Two add-ons worth knowing before you budget: managed databases start at $15/month, and DDoS protection is $10/month on plans that offer it. Neither is included in the instance price.

The size ladder inside each family is long. Cloud Compute alone runs past a hundred size combinations, from the $2.50 box up to four-figure monthly configs. That's the practical argument for hourly metering: you can start on the $12 tier, watch real CPU and memory for a week, and move up one step rather than guessing at a two-year commitment. Vultr also sells reserved capacity for workloads you know will stay put, which costs less per hour than on-demand.

The $2.50 and $6 tiers are for things that don't need to be fast. A WordPress site with a caching plugin and a few hundred daily visitors will run there. A WooCommerce store processing checkout requests will not, and moving to the $12 High Performance tier buys NVMe storage and a current-generation CPU for the price of two coffees.

## Cloud hosting vs VPS vs shared vs dedicated

The four traditional categories differ in where your resources physically sit, and that single fact drives the pricing model, the failure behavior and how much of the sysadmin work lands on you.

|  | Shared | VPS | Dedicated | Cloud |
| --- | --- | --- | --- | --- |
| **Architecture** | One server, many sites | One server split by a hypervisor | One physical box, single tenant | Networked virtual servers across hosts |
| **Scaling** | Capped by that server | Capped by that machine | Capped by the hardware | Add or drop capacity without migrating |
| **Billing** | Fixed monthly or annual | Fixed monthly | Fixed, high | Metered, hourly or monthly |
| **Hardware failure** | Site goes down | Site goes down | Site goes down | Another server takes over |
| **Who patches the OS** | Host | You | You | You, on self-managed cloud servers |

The scaling row is the one that matters most for a growing project. A VPS gives you more control and isolation than shared hosting, but your ceiling is the physical machine you were placed on. If that machine runs out of headroom, you're stuck waiting for the host or migrating. Cloud hosting spreads your workload across a pool, so capacity is a setting rather than a move.

Where each one wins:

**Shared hosting** is enough for a brochure site, a personal blog, or a first WordPress install with low traffic. You get a control panel, the host handles maintenance, and the cost is the lowest of the four. The trade-off is that your site's ceiling is set by a server you share with strangers, and load from those strangers can show up as slowness on your pages.

**A VPS** is the right answer when you need root access, a specific OS or kernel, or a fixed monthly bill you can predict to the cent. It's also the cheaper option for a single always-on workload with steady traffic: a $5–$6 VPS does roughly what a $6 cloud instance does, minus the failover and the instant resize.

**Dedicated hardware** exists for licensing that counts cores or sockets, for I/O patterns that virtualisation gets in the way of, and for compliance rules that forbid sharing. It's also the most expensive and the least flexible, and you're the one managing it.

**Cloud** pays off when your load is uneven, when downtime costs more than the price gap, or when you need servers in more than one region. The distributed architecture is what buys the reliability: if one host fails, another picks up the workload, and content served from a nearby region reaches users with less latency.

One clarification that saves confusion when you're reading vendor pages: web hosting doesn't have to involve cloud computing. Plenty of hosts describe a single virtual server as "cloud hosting" because it sits in a data centre that also runs cloud infrastructure. The defining traits are the pooled resources, the metered billing and the ability to scale without a migration.

## Where hourly billing saves money, and where it leaks

Pay-as-you-go pricing solves a real problem: you stop provisioning for your worst day. Instead of buying a server sized for Black Friday and paying for it in March, you run a modest instance most of the year and add capacity when traffic arrives. Serverless platforms take this further, charging only while your code executes and scaling to zero when nobody is visiting.

The leak is that metered billing charges for what exists, not for what's busy. An idle $12 instance costs the same as a loaded one. A test server you spun up in March and forgot about bills straight through November. Anyone who has managed cloud infrastructure has a story about a forgotten snapshot or a staging box someone left running; the fix is a habit of destroying instances rather than leaving them parked, and checking the billing dashboard in week one.

The arithmetic is friendly at small scale. At $12/month, an instance costs roughly $0.016 per hour, so a three-day experiment runs about $1.20. That's the argument for testing on the tier above what you think you need: the price difference between the $6 and $12 tiers is about $0.008 an hour, and finding out that your app needs 2 GB of RAM on day one is cheaper than finding out in production.

👉 [Start on a small Vultr instance and resize it later](https://bit.ly/VuLtr)

## What the $300 credit actually is

Vultr's coupons page currently lists four offers for new customers:

| Code | What it gives you |
| --- | --- |
| VULTRMATCH | Vultr matches your first deposit dollar for dollar, up to $100 |
| FLYTWOHUNDRED | $200 promotional credit |
| 250VULTRFLY | $250 promotional credit |
| FLY300VULTR | $300 promotional credit |

All four carry the same footnotes: promotional credit applies to select products only, cannot be combined with any other offers, new customers only, restrictions and terms apply.

Read those footnotes before you plan around the number. Three things follow from them.

**You pick one.** The codes don't stack. If you're putting real money in, the deposit match behaves differently from the credit: matched funds sit alongside your own deposit, while the $300 is promotional credit that offsets eligible charges. For a first project where you intend to spend $50 anyway, the match can be the better deal; for pure evaluation with no intention of prepaying, the $300 code buys more testing time.

**Credit is not cash.** It offsets eligible products on your bill. It isn't withdrawable, it doesn't transfer, and the "select products" line means you should confirm your intended plan is covered before you build a month of testing around it. Compute instances are the core of what these offers target, but the terms are the authority, not the banner.

**There's no free tier and no free trial.** Vultr doesn't publish a permanent free plan, so the credit is the trial. Plan to attach a payment method, and treat the credit as something to spend in weeks rather than months, since promotional credit carries an expiry set out in the terms shown at signup.

👉 [Claim the $300 credit on a new Vultr account](https://bit.ly/VuLtr)

## What you're on the hook for after the server boots

Cloud security is shared between the provider and you, and the split depends on how much of the stack you're renting.

The provider handles the physical side: data centre access controls, the hypervisor, the network, and patching the underlying platform. On Vultr, that's what your instance fee covers. What it doesn't cover is the operating system inside your instance, the application running on it, the libraries it depends on, and your credentials. On a self-managed cloud server, those are yours. Every kernel update, every framework security release, every SSH key you forget to rotate.

Managed and serverless products shift more of that responsibility to the provider, and the price reflects it. This is the real division between "cloud hosting" and "managed cloud hosting", and it's the line most plan comparisons skip. If you can't patch a Linux box and don't want to learn, an unmanaged $12 instance is not cheaper than a managed plan at twice the price; it's a future incident.

Backups are a separate decision again. Cloud hosts provide snapshot and backup mechanisms you can bolt on for disaster recovery, but they're usually an add-on rather than a default, and a snapshot you never tested is a file, not a recovery plan.

## Common questions

**Is cloud hosting faster than a VPS?**
Not automatically, and raw speed is the wrong comparison. A VPS and a cloud instance can run identical hardware. The difference shows up under failure and under load: cloud spreads across hosts and adds load balancing and CDN options, so a single hardware fault doesn't take your site down, and traffic spikes are absorbed rather than queued. If your only concern is single-request latency, a well-specced VPS competes fine.

**When is shared hosting enough?**
When you have one low-traffic site, no need for root access, and no expectation of a traffic event you'd have to survive. The moment you need a custom daemon, a specific PHP or Node version, or the ability to survive a neighbour's traffic spike, you've outgrown it.

**Serverless or a cloud server?**
Serverless charges only while your code runs and scales to zero between requests, which suits spiky or intermittent workloads and teams without server-management experience. A cloud server gives you an OS, persistent local state, and predictable behaviour for long-running processes. Cron jobs, WebSocket servers and anything with a local cache want the server.

**Do I still pay when the server is idle?**
On an hourly-billed instance, yes. You're renting the reservation, not the CPU cycles. That's why the destroy-it-when-you're-done habit matters, and why serverless pricing exists for workloads that are idle most of the day.

**Does cloud hosting include a control panel like cPanel?**
Not by default. Vultr sells infrastructure: you get a server and root access, and you install whatever panel or stack you want. If you'd rather not touch a command line, look at managed hosting instead of raw cloud compute.

## How to decide

Match the workload to the family, then size one step above your guess and watch the metrics for a week.

- **Static site, docs, landing pages** → Regular Performance at $2.50/month, or push the files to object storage with a CDN in front and skip the server entirely.
- **WordPress or a small app with caching** → High Performance at $12/month. The NVMe storage is the part you'll notice.
- **API or app with real concurrency** → High Performance, then step up within the family as CPU graphs tell you to.
- **Database, queue worker, anything pinned at high CPU** → Optimized Cloud Compute with dedicated vCPU, from about $28/month. Shared cores are the wrong tool for sustained load.
- **Traffic you can't predict, or a workload that's idle most of the day** → serverless, so idle costs nothing.
- **Root access, fixed bill, one always-on service** → a $5–$6 VPS is honestly cheaper. Buy cloud when failure or resizing actually costs you money.

Three things to confirm before you enter a card: the billing granularity (Vultr meters hourly, so short tests are cheap), which products the promotional credit covers and when it expires, and whether the plan you're eyeing includes backups or charges extra for them.

👉 [Compare Vultr's plans and pick a size](https://bit.ly/VuLtr)
