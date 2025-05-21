# Is this software *the* best software for this?
This is the most important question to ask ourselves when looking for a software to do something, or when making a software to do something. I'll get rid of any case-specific goals, to focus on general ones. We can list a few things :
- Speed, because we want it to go as fast as possible
- Security, because we do not want our computer to be hacked
- Flexibility, because the environment of the software may change over time and we don't want that to break it
- Simplicity, because we do not want to spend hours trying to figure out how to use the software

These, are the base goals that should be reached by any software.

## Speed
Until we find out how to get infinite compute power, speed will matter, for three reasons :
- Support for lower-end computers
- Using less resources, so less electricity used and more time for other softwares to run
- Being happy because things go quickly (a slow software is an incredible workflow breaker)

## Security
This concern is so important that there is a whole branch of informatic dedicated to it. This is why it *must* be achieved.

## Flexibility
This is mostly to allow the software to run correctly, even outside of its expected environment, which may mean just changing the name of a few folders, to the location of the libraries and executables, to the running services, to even the running kernel. The more flexible a software it, the more users it can be used by and the longer it will work on modern environment.
It also means an other thing, which is allowing users to do whatever they want with the software, not having the software telling them what they can and what they can't do. To clarify, here a some examples :
- Enforcing strict naming conventions for variables in a programming language - OK
- Requiring the presence of Google Play Services for a simple calculator - NOT OK
- Warning a lot the user about how dangerous modifing an essential file is - OK
- Preventing the user to modify an essential system file without any way to bypass it - NOT OK (except in some situations, when the user do not own the device, like a corporate computer)

## Simplicity
We are humans, and as humans we also do not have infinite compute power. This is why the closer the software is from what we are used to do, so the simpler it is, the quicker we can use it to enjoy it. The only objection I found to this, is making finding security problems harder, but this also means that the software may be insecure, plus it also prevent "grey hats" to find security problems to report them by themselves.

# Order of importance
Not all of these are as important as the others, this is why some can be sacrificed to achieve a more important goal. These are what I found to be the most important :
1. Security
2. Speed
3. Simplicity
4. Flexibility