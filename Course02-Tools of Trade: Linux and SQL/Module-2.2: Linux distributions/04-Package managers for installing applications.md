
# Package Managers for Installing Applications on Linux

## Introduction to Package Managers

- **Definition:** A package is a piece of software that includes files necessary for installation.
- **Dependencies:** Supplementary files required for running an application are bundled with packages.
- **Role of Package Managers:** Tools to install, manage, and remove packages on Linux.

## Types of Package Managers

### Debian-Derived Distributions (e.g., Ubuntu, KALI LINUX™, Parrot)

- **Package Manager:** dpkg
  - **File Extension:** .deb (e.g., Package_Version-Release_Architecture.deb)
  
- **Package Management Tool:** Advanced Package Tool (APT)
  - **Functionality:** Command-line interface for managing, searching, and installing packages.

### Red Hat-Derived Distributions (e.g., Red Hat Enterprise Linux, CentOS)

- **Package Manager:** Red Hat Package Manager (RPM)
  - **File Extension:** .rpm (e.g., Package-Version-Release_Architecture.rpm)
  
- **Package Management Tool:** Yellowdog Updater Modified (YUM)
  - **Functionality:** Command-line tool for managing, searching, and installing .rpm packages.

## Package Management Tools

- **Advanced Package Tool (APT):**
  - **Used in:** Debian-derived distributions.
  - **Function:** Manage packages from the command line, including installation and updates.

- **Yellowdog Updater Modified (YUM):**
  - **Used in:** Red Hat-derived distributions.
  - **Function:** Command-line tool to manage .rpm packages, handling installation and updates.

## Key Considerations

- **Choosing the Right Tool:** Select package managers and tools based on the Linux distribution's origin (Debian or Red Hat).
- **File Extensions:** .deb for dpkg (Debian), .rpm for RPM (Red Hat).
- **Security and Updates:** Always use the latest package versions for security and bug fixes.
