# Lab 01: Linux Fundamentals

## Objective

The goal of this lab was to become familiar with basic Linux commands and identify the environment used for the lab.

## Environment

- Operating system environment: Ubuntu on Windows Subsystem for Linux 2 (WSL2)
- Shell: Bash-compatible terminal
- Architecture: x86_64
- Project directory: `/home/juls0/linux-networking-labs`

## Tools and Commands

### 1. `pwd` - Print Working Directory

**Purpose:** Displays the current working directory.

**Command:**
```bash
pwd
```

**Observed result:**
```text
/home/juls0/linux-networking-labs
```

**What I learned:** This command confirms the location of my project files and helps me verify that I'm working in the correct directory.

### 2. `ls -la` - List Files and Directories

**Purpose:** Lists directory contents, including hidden entries, with detailed information.

**Command:**
```bash
ls -la
```

**Observed findings:**
- `labs/` directory exists.
- `findings/` directory exists.
- `screenshots/` directory exists.

**What I learned:** The detailed listing shows file permissions, ownership, sizes, and modification times. The `-a` option includes hidden entries, while `-l` displays details in a long format.

### 3. `whoami` - Identify the Current User

**Purpose:** Displays the username of the current user.

**Command:**
```bash
whoami
```

**Observed result:**
```text
juls0
```

**What I learned:** Knowing which account I'm using helps me understand the permissions and access associated with my terminal session.

### 4. `uname -a` - Display System Information

**Purpose:** Displays kernel and system information.

**Command:**
```bash
uname -a
```

**Observed result summary:**
- Kernel: Linux
- Hostname: `JD-Computer`
- Kernel release: `6.18.54.1-microsoft-standard-WSL2`
- Architecture: `x86_64`

**What I learned:** The kernel information identifies this environment as WSL2. This helps distinguish a Linux environment running through Windows from a separate physical Linux machine.

## Security Observations

1. **User context matters:** Identifying the current account is useful when checking permissions and investigating system activity.
2. **File permissions matter:** The `ls -la` command provides information that can help identify files with unexpected permissions.
3. **Environment identification matters:** Knowing that a system uses WSL2 helps determine which operating system and networking layers are relevant during troubleshooting.

These are initial observations, not evidence of a security vulnerability.

## Conclusion

In this lab, I practiced four foundational Linux commands and confirmed that my project directories were present. I also identified my Linux environment as WSL2 running on an x86_64 architecture.

This lab established a foundation for further work with Linux file permissions, network interfaces, routing, DNS, and connectivity troubleshooting.

## Next Steps

- Explore Linux file permissions in more detail.
- Inspect network interfaces and routing.
- Perform DNS lookups and connectivity tests.
- Document findings and security considerations from each lab.

