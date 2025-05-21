# Kernel
*AvalancheOS's kernel will be a separate project.*
The base kernel is itself as barebone as possible : just a simple module handling system. Every functionnalities are added by modules. Here's how it works :

There are two categories of modules :
- Interface
- Implementation

Interface modules just specify what system calls it adds, and what parameters there are. They are extremely simple.

Implementation modules are what is called a driver, they implement the interfaces. At least one implementation module must be loaded in order to activate an interface. Implementation modules may depend on other interfaces, but not on any other implementations. They may also depend on some hardware features.

# Boot process
The base kernel hard-linked with the module loader is first loaded with the UUID of System partition and the UUID of the User partition, along with a simple `tmpfs` containing the modules to load. When the kernel is executed, it calls the module loader, which will parse the `tmpfs` to get all the modules to load, and calls the kernel each time it shoud load a module. Then, a tiny module depending on filesystems will mount the System and User partitions, and will call the System Manager, with Process ID 0. From now, the System Manager will load every userspace services.

# Some notes
Some services which are in other operating systems running as userspace programs may be runned as kernel modules. However, if a module can, it will be ran at ring 3.