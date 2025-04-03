<p align="center">
  <img alt="Osmedeus" src="https://raw.githubusercontent.com/osmedeus/assets/main/logo-transparent.png" height="140" />
  <br />
  <strong>Osmedeus - A Workflow Engine for Offensive Security</strong>

  <p align="center">
  <a href="https://docs.osmedeus.org/"><img src="https://img.shields.io/badge/Documentation-0078D4?style=for-the-badge&logo=GitBook&logoColor=39ff14&labelColor=black&color=black"></a>
  <a href="https://docs.osmedeus.org/donation/"><img src="https://img.shields.io/badge/Sponsors-0078D4?style=for-the-badge&logo=GitHub-Sponsors&logoColor=39ff14&labelColor=black&color=black"></a>
  <a href="https://twitter.com/OsmedeusEngine"><img src="https://img.shields.io/badge/%40OsmedeusEngine-0078D4?style=for-the-badge&logo=Twitter&logoColor=39ff14&labelColor=black&color=black"></a>
  <a href="https://discord.gg/mtQG2FQsYA"><img src="https://img.shields.io/badge/Discord%20Server-0078D4?style=for-the-badge&logo=Discord&logoColor=39ff14&labelColor=black&color=black"></a>
  <a href="https://github.com/j3ssie/osmedeus/releases"><img src="https://img.shields.io/github/release/j3ssie/osmedeus?style=for-the-badge&labelColor=black&color=2fc414&logo=Github"></a>
  </p>
</p>

---

## Osmedeus Workflow

Workflow is part of Osmedeus which is a collection of YAML files that describe your methodology.

## Installation for Linux

> NOTE that you need some essential tools like `curl, wget, git, zip` and login as **root** to start

```shell
bash <(curl -fsSL https://raw.githubusercontent.com/osmedeus/osmedeus-base/master/install.sh)
```

## Anatomy of the Public Community methodology

![community-workflow](https://raw.githubusercontent.com/osmedeus/documentation/main/src/static/workflow/community-workflow.png)

![general workflow](https://raw.githubusercontent.com/osmedeus/assets/main/general-workflow-mindmap.png)

## Usage

Check out [this page](https://docs.osmedeus.org/installation/usage#scan-actually-start-a-scan-based-on-predefined-workflow) to see how this workflow can be use to scan

```shell
# Scan Usage:
  osmedeus scan -f [flowName] -t [target]
  osmedeus scan -m [modulePath] -T [targetsFile]
  osmedeus scan -f /path/to/flow.yaml -t [target]
  osmedeus scan --threads-hold=30 -f cidr -t 1.2.3.4/24
  osmedeus scan -m /path/to/module.yaml -t [target] -l /tmp/log.log
  cat targets | osmedeus scan -f sample

# Practical Scan Usage:
  osmedeus scan -T list_of_targets.txt -W custom_workspaces
  osmedeus scan -t target.com -w workspace_name --debug
  osmedeus scan -f general -t sample.com
  osmedeus scan --tactic aggressive -f general -t sample.com
  osmedeus scan -f extensive -t sample.com -t another.com
  cat list_of_urls.txt | osmedeus scan -f urls
  osmedeus scan --threads-hold=30 -f cidr -t 1.2.3.4/24
  osmedeus scan -m ~/.osmedeus/core/workflow/test/dirbscan.yaml -t list_of_urls.txt
  osmedeus scan --wfFolder ~/custom-workflow/ -f your-custom-workflow -t list_of_urls.txt
  osmedeus scan --chunk --chunk-part 40 -c 2 -f cidr -t list-of-cidr.txt

# Queue Usage:
  osmedeus queue -Q /tmp/queue-file.txt -c 2
  osmedeus queue --add -t example.com -Q /tmp/queue-file.txt

# Provider Usage:
  osmedeus provider wizard
  osmedeus provider validate
  osmedeus provider build --token xxx --rebuild --ic
  osmedeus provider create --name 'sample'
  osmedeus provider health --debug
  osmedeus provider list
  osmedeus provider delete --id 34317111 --id 34317112

# Cloud Usage:
  osmedeus cloud -f [flowName] -t [target]
  osmedeus cloud -m [modulePath] -t [target]
  osmedeus cloud -c 5 -f [flowName] -T [targetsFile]
  osmedeus cloud --token xxx -c 5 -f [flowName] -T [targetsFile]
  osmedeus cloud --chunk -c 5 -f [flowName] -t [targetsFile]

# Utilities Usage:
  ## Health check utility
  osmedeus health
  osmedeus health git
  osmedeus health cloud
  osmedeus version --json
  ## Update utility
  osmedeus update
  osmedeus update --vuln
  osmedeus update --force --clean
  ## Other utilities
  osmedeus utils tmux ls
  osmedeus utils tmux logs -A -l 10
  osmedeus utils ps
  osmedeus utils ps --proc 'jaeles'
  osmedeus utils cron --cmd 'osmdeus scan -t example.com' --sch 60
  osmedeus utils cron --for --cmd 'osmedeus scan -t example.com'
  osmedeus utils workflow
  osmedeus config set --threads-hold=10
```

## 👨‍💻 Contribute

If you have found some valuable tool or suggest to use the tool in each module better feel free to open an issue for just DM me via [@j3ssiejjj](https://twitter.com/j3ssiejjj).

## 💬 Community & Discussion

Join Our Discord server [here](https://discord.gg/mtQG2FQsYA)

## 💎 Donation & Sponsor

<p align="center">
 <img alt="Osmedeus" src="https://raw.githubusercontent.com/osmedeus/assets/main/premium-package.gif" />

 <p align="center"> Check out for a couple of <strong><a href="https://docs.osmedeus.org/donation/">donation methods here</a></strong> to get a <strong><a href="https://docs.osmedeus.org/premium/">premium package</a></strong><p>
</p>

## License

`Osmedeus` is made with ♥ by [@j3ssiejjj](https://twitter.com/j3ssiejjj) and it is released under the MIT license.
