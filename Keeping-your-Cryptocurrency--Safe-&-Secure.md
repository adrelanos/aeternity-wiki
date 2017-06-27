[Cryptocurrency](https://en.wikipedia.org/wiki/Cryptocurrency) has changed the way we use currency. It allows us to be
in a sense our own bankers and it provides us with new ways to buy and
sell products. However, it brings with it one of the inherent problems
that all other currencies have whether it's paper money or digital
currency. Malicious users and thieves will go to just about any length
necessary in order to obtain your hard earned digital currency.  
They don't care about who you are, how nice a person or how adversely
affected you will be from them stealing from you.

It seems like everyday we hear a story about someone either losing their
digital currency or having had it stolen by a malicious user. In many of
those cases, had the victim implemented a few simple security measures,
their digital currency would not have been stolen. This does not mean
that you can follow all the security practices on the page and you will
have nothing to worry about. Unfortunately, there is nothing that can be
done to prevent a gifted attacker that is committed to gaining entry
into your computer. The best you can do is to use the security best
practices below in an effort to mitigate the majority of these threats.

***

## TOC

* [Security Best Practice](#security-best-practices)
  * [Physical Security](#physical-security)
  * [Choosing an Os](#choosing-an-os)
    * [Open-source v.s. Proprietary](#open-source-vs-proprietary)
    * [Proprietary OS](#proprietary-os)
    * [Open Source OS](#open-source-os)
       * [User Account Privileges](#user-account-privileges)
       * [Social Engineering](#social-engineering)
       * [Separateness of Environments](#separateness-of-environments)
       * [How many eyes see the code](#how-many-eyes-see-the-code)
    * [Choosing Your Linux Distribution](#choosing-your-linux-distribution)
       * [Debian](#debian)
          * [Advantages Debian](#advantages-debian)
       * [Qubes](#qubes)
          * [Advantages Qubes](#advantages-qubes)
       * [Whonix](#whonix)
         * [Advantages Whonix](#advantages-whonix)
       * [Tails](#tails)
         * [Advantages Tails](#advantages-tails)
  * [BIOS Passwords](#bios-passwords)
  * [Full Disk Encryption](#full-disk-encryption)
  * [Passwords](#passwords)
    * [Security implications passwords](#security-implications-passwords)
  * [Password Managers](#password-managers)
    * [Security implications password managers](#security-implications-password-managers)
  * [Man in the middle attacks](#man-in-the-middle-attacks)
    * [Defense and Detection MITM attacks](#defense-and-detection-mitm-attacks)
  * [Authentication](#authentication)
  * [Tamper detection](#tamper-detection)
  * [Cryptocurrency Wallets](#cryptocurrency-wallets)
     * [Software Wallets](#software-wallets)
     * [Hardware Wallets](#hardware-wallets)
     * [Mnemonic Recovery Passphrase](#mnemonic-recovery-passphrase)
  * [Afterword](#afterword)
  * [Additional WARNINGS](#additional-warnings)

[☝](#toc)
[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#toc)
## Security Best Practices

### Physical Security

The first thing that we will go over is physical security. This means
restricting physical access to your computer and hardware wallets. How
do we do this? It starts with following the dos and don'ts.

* If you are leaving your house it is a good idea to put your laptop and
  hardware wallet in a safe. Not all of us have a safe in our home,
  however they are worth the money if we have something of value.
  Otherwise, if no safe is available, hiding your hardware in a place
  that is hard to find is another option even if its a linen closet or
  under a blanket in your bedroom. Remember a thief who steals your
  laptop may not even know that there is software wallet on your
  computer filled with currency. The thief just sees a valuable laptop
  for the taking. The same thing goes for hardware wallets. The thief
  may not even know what a hardware wallet is, all he cares about is
  that it could have value.

* Never leave your laptop or hardware wallet in a public place. If you
  do take them into a library or classrooms, do not leave them alone,
  not even for a minute while you go to the restroom or out to your car.
  Thieves look for such opportunities. However, if you must leave your
  laptop unattended in a public place, lock it up with a [Kensington](https://en.wikipedia.org/wiki/Kensington_Security_Slot)
  lock.

* Never leave your laptop or [hardware wallet](https://en.bitcoin.it/wiki/Hardware_wallet) unattended in your office
  or dorm room. Once again if you must step out for a moment, use a
  Kensington lock. Remember thieves will go after what is easiest for
  them to steal. If they have a choice between 2 identical laptops and 1
  of them is secured with a Kensington lock, which one do you think they
  will go for? They will take the path of least resistance and steal the
  laptop that does not have a notebook lock.

* If you have to leave your laptop or hardware wallet in a car, put them
  in a bag and put the bag in the trunk. It is preferable that you stop
  somewhere before you reach your destination so potential thieves don't
  see you putting your hardware into the trunk.

<hr>

[☝](#toc)
### Choosing an Os
Choosing an operating system is arguably the single most important
decision that you will make when it comes to keeping your digital
currency safe and secure. With so many operating systems to choose from
how do we decide which one best suits our needs? First we will have to
decide what our needs are. Since this paper focuses on keeping our
digital currency secure, will require a open-source OS. Why do we need
an open-source operating system and not say, that wonderful OS named
Windows? Well, that is one of the questions we are going to answer along
with a few others on our journey to find the right OS.

[☝](#toc)
#### open-source-vs-proprietary
[open-source](https://en.wikipedia.org/wiki/Open-source_model), we all have heard those words before, but what do they
mean? Simply stated open-source is a decentralized (just like aeternity)
developmental model that encourages open collaboration between peers and
making products such as source code and documentation freely available
to the public. Open-source code is meant to be a collaborative effort,
where programmers improve upon the source code and share the changes
within the community. Code is released under the terms of a software
license. Depending on the license terms, others may then download,
modify, and publish their version (fork) back to the community.


Now that you have a basic understanding of open-source lets move onto
[proprietary](https://en.wikipedia.org/wiki/Proprietary_software) (also referred to as closed-source) software. Relatively
speaking proprietary software is the opposite of open-source software.
Proprietary software is computer software for which the software's
publisher or another person retains intellectual property
rights--usually copyright of the source code. What this means is the
public can not download, modify, or publish their version of the
software without the express permission of the software's publisher.


In most cases the publisher will not let anyone see the source code out
of fear that trade secrets or the source code will be stolen. You may be
wondering what all this has to do with keeping our digital currency
safe. Well, we are about to get to that now that we know the difference
between open-source and proprietary software.

[☝](#toc)
#### Proprietary OS
Proprietary operating systems like Windows has many more users than Mac
and Linux combined. Since they have all of these user does it mean that
is is more secure? Why else would so many people use them?

To answer the the question. Most people are using it because it has all
the bells and whistles and it's easy to use. No only that Microsoft puts
millions upon millions of dollars every year into marketing. Just
because more people use an operating system does not by any means make
an OS more secure. What makes Windows OS insecure is that the source
code is closed-source.

Microsoft if very strict about who they let see the source code. When
they do show the source code its only to their clients (like the
government) but only after signing a [non-disclosure agreement](https://en.wikipedia.org/wiki/Non-disclosure_agreement). This way
if someone were to steal trade secrets or tell the public what they saw
there would be severe legal repercussions.

What this means is that no independent security audits can be performed
and published on Windows OS. There is no way for the public to know if
there are any major security holes in the OS. We just have to take
Microsoft at it word that there are no back doors (insert laughter) or
security vulnerabilities (laughing even harder).

[☝](#toc)
#### Open Source OS

Open-source operating systems like Linux do not have nearly as many user
as Window but they are much more secure. The source code is freely
available for everyone to see. This means that independent security
audits can be performed to make sure there are no major vulnerabilities
present. This also means that there are many more eyes looking at the
source code and therefore reporting security issues to the developers
much quickly than if it was closed-source. Many times bugs are reported
and patched before the security vulnerability can be exploited.

If there is a backdoor to the OS it would be found and reported very
quickly. This is all because Linux is open-source. ### Now that we have
a good understanding of proprietary and open-source we can discuss other
reasons why an open-source Linux distro is more secure than a
closed-source Windows OS.

***

[☝](#toc)
#### User Account Privileges

In Windows, users are generally given administrator privileges by
default which means they have access to everything on the system. If the
virus is able to penetrate their system, they can quickly gain access to
important parts of the system. On the other hand, in Linux, users are
given lower level access rights, and, theoretically, the virus can only
access the users local files and folders thus preventing malicious code
from infecting the entire system.

***

[☝](#toc)
#### Social Engineering
Closed-source operating systems like Windows
  are more vulnerabilities to social engineering attacks. Most viruses
  are spread by convincing users to doing something they shouldn't, like
  opening up an email attachment that is carrying a virus or worm or
  clicking on a malicious link.

  What makes Linux less susceptible to these types of attacks is that
  most Linux users don't have root access however, it's much harder to
  accomplish any real damage on a Linux system by getting them to do
  something foolish. Before any real damage could be done, a Linux user
  would have to read the email, save the attachment, give it executable
  permissions and then run the program. Not very likely, in other words.

***

[☝](#toc)
#### Separateness of Environments
 Linux works in many environments and
  distros such as Debian, Qubes, Arch, and many others. With Various
  email clients, shells and packaging systems that makes the system
  extremely fragmented and difficult for any virus. So, whereas a virus
  can be targeted squarely at Windows users, since for the most part use
  the same technology, reaching more than a small fraction of Linux
  users is much more difficult.

***

[☝](#toc)
#### How many eyes see the code
 As stated above Windows source code is
  closed-source and has a limited set of paid developers who try to find
  the problems in the code. Windows devs would have you believe this is
  a good thing. They want you to believe that its a good thing that only
  the paid devs can see the source code. The phrase they like to use is
  "security through obscurity", which is a very common term and I'm sure
  you have heard of it. The expression is intended to suggest that
  proprietary software is more secure by virtue of its closed nature. If
  hackers can't see the code, then it's harder for them to create
  exploits for it: or so the thinking goes. Unfortunately for Windows
  users, that's just not true. Linux on the other hand has a larger
  group of developers and testers working on a set of code, this makes
  it much more likely any flaws will be caught and fixed quickly. This,
  in other words, is essentially the polar opposite of the "security
  through obscurity" argument. Not only that, but Linux users can fix
  problems themselves. Microsoft may tout its large team of paid
  developers, but it's unlikely that team can compare with a global base
  of Linux user-developers around the globe.

[☝](#toc)
### Choosing Your Linux Distribution

With so many Linux distros: also referred to as flavors of Linux, how do
we decide which one to use. Many people will tell you they are all the
same and it comes down to user preference. However, although many may
share the same Linux kernel, there are some major differences in the
distributions. Since we are focusing on keeping our digital currency
safe and secure we want a distro that focuses on security and stability.

[☝](#toc)
#### [Debian](https://www.debian.org/)
 Debian is well known for its security and
stability and sets itself apart by being the largest and most
comprehensive Linux distribution ever created having well over 1,000
volunteers working on the project since 1993. Because of this many
derivatives of Linux distros are based off of Debian, and it has become
the grandfather of a large family of Linux distributions.


##### Advantages Debian
* Efficient and well integrated packaging for a more robust system.
* Full disk encryption
* iptables - a user-space application program that allows users to
  configure the tables provided by the Linux kernel firewall
  (implemented as different Netfilter modules) and the chains and rules
  it stores.
* SELinux - Linux kernel security module that provides a mechanism for
  supporting access control security policies.
* Publicly available bug tracking system.
* Stability - some users report running Debian 1+ year without a single
  reboot!
* Security - being 100% open, security issues are exposed and plugged
  quickly.

***

[☝](#toc)
#### [Qubes](https://www.qubes-os.org/)**
Qubes is a security-focused desktop
operating system that aims to provide security through isolation. In
order to secure a desktop, a Qubes user should take care of isolating
various environments, so that if one of the components gets compromised,
the malicious software would get access to only the data inside that
environment. With Qubes The assumption is that there can be no perfect,
bug-free desktop environment. Such an environment counts millions of
lines of code, billions of software/hardware interactions. To provide
isolation, Qubes leverages virtualization through the Xen hypervisor to
provide isolation between two different qubes. User environments can be
based on Fedora, Debian, Whonix, and Windows, among other operating
systems.

##### Advantages Qubes

* The Xen hypervisor and administrative domain (dom0) in Qubes OS
  actively discourages any activity other than running VMs.
* The network stack and Wi-Fi drivers are running in a dedicated,
  unprivileged network VM (NetVM), which substantially reduces the
  attack surface.
* An additional firewall VM is used to house the Linux kernel-based
  firewall, providing extra protection against a compromised NetVM.
* By default, Qubes OS is firewalled and no incoming ports are open.
* No networking is present in the administrative domain (dom0). Even
  dom0 upgrades are done in a dedicated UpdateVM. (currently set by
  default to NetVM), before those are verified and installed in dom0.
* DisposableVMs are available to open untrusted applications, links,
  attachments and documents.
* Greater security of email-centric work environments is possible by
  using split GPG to protect private keys and  
  limiting network connections exclusively to the chosen email server.
* Protection against unintentional leaks of critical user data is
  possible by setting an empty NetVM field for the corresponding qube.

***

[☝](#toc)
#### [Whonix](https://www.whonix.org/wiki/Main_Page)
Whonix is a desktop
operating system designed for advanced security and privacy. Whonix
mitigates the threat of common attack vectors while maintaining
usability. Online anonymity is realized via fail-safe, automatic, and
desktop-wide use of the [Tor](https://en.wikipedia.org/wiki/Tor_%28anonymity_network%29) network. A heavily reconfigured Debian base
is run inside multiple virtual machines, providing a substantial layer
of protection from malware and IP address leaks. Commonly used
applications are pre-installed and safely pre-configured for immediate
use. The user is not jeopardized by installing additional applications
or personalizing the desktop. Whonix is under active development and is
the only operating system designed to be run inside a virtual machine
and paired with Tor.


##### Advantages Whonix

* Based on Debian, which is well known for its security and stability.
* Only connections through the Tor network are permitted
* Servers can be run, and applications used anonymously over the
  internet.
* DNS leaks are impossible
* Malware with root privileges cannot discover the user's real IP
  address.
* Threats posed by misbehaving applications and user error are
  minimized.

[☝](#toc)
#### [Tails](https://tails.boum.org/)
Tails (which stands for ‘The Amnesiac
Incognito Live System’) is probably the most well known privacy-focused
distro however its features also make it a very secure OS. It can be run
from a DVD in Live mode whereby it loads entirely into your system RAM
and will leave no trace of its activity. The OS can also be used in
‘persistent’ mode where your settings can be stored on an encrypted USB
stick. All connections are routed through the anonymity network Tor,
which conceals your location. The applications in Tails have also been
carefully selected to enhance your privacy and security.

##### Advantages Tails

* Tails is amnesiac which means that when you reboot the OS any changes
  that were made to it in that session are  
  erased. So if a malicious user was to infect your computer with a
  virus or worm it would no longer be there after you reboot the system.
  Keep in mind that if you are infected with a virus during that a
  session all the work you did during that session could be compromised.
  If you entered your password into your web wallet the malicious user
  could very well have your password.
* The Tails devs have already tested and configured much of the software
  for you. Most of the applications you will need come pre-installed.
* Uses state-of-the-art cryptographic tools to encrypt your files,
  emails and instant messaging. .

***

[☝](#toc)
### BIOS Passwords

Let’s say you’ve followed good security practices and have a password
set on your Linux user account. When your computer boots, someone will
have to enter your Linux user account password to use it or access your
files, right? Not necessarily.

The person could insert a removable device like a USB drive, CD, or DVD
with a live operating system on it. They could boot from that device and
access a live Linux desktop if your files are unencrypted, they could
access your files. A user account password doesn’t protect your files.

You could change the boot order to force the computer to always boot
from its internal hard drive, but someone could enter your BIOS and
change your boot order to boot the removable device.

A [BIOS](https://en.wikipedia.org/wiki/BIOS) password provides some protection against this. Depending on how
you configure the password, people will need the password to boot the
computer or just to change BIOS settings.

Of course, if someone has physical access to your computer, all bets are
off. They could crack it open and remove your hard drive or insert a
different hard drive. Physical access enables a malicious actor to easily
reset and bypass the BIOS password. A BIOS password still does provide 
extra protection here,particularly in situations where people have access
to a keyboard and USB ports, but the computer’s case is locked up and they
can’t open it.

These passwords are set in your BIOS settings screen. You’ll need to
reboot your computer and press the appropriate key during the boot-up
process to bring up the BIOS settings screen. This key varies from
computer to computer, but is often F2. If you need help, look at your
computer’s documentation.

In the BIOS settings screen, locate the password option, configure your
password settings however you like, and enter a password. You may be
able to set different passwords for example, one password that allows
the computer to boot and one that controls access to BIOS settings.

You’ll also want to visit the Boot Order section and ensure the boot
order is locked down so people can’t boot from removable devices without
your permission.

***

[☝](#toc)
### Full Disk Encryption

Disk encryption is a technology which protects the information on your
hard drive, USB, or CD by converting it into unreadable code that cannot
be deciphered easily by unauthorized people. Disk encryption uses
encryption software of hardware to encrypt all of the data that goes on
a disk or disk volume Disk encryption prevents unauthorized access to
the data stored on the disk.

What we will be focusing on is referred to as Full Disk Encryption. You
would think--from the name--that full disk encryption signifies that
everything on the disk is encrypted: however the [master boot record](https://en.wikipedia.org/wiki/Master_boot_record)
(MBR) or the [Unified Extensible Firmware Interface](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface) (UEFI) which is the
code that starts the OS loading sequence, is not encrypted. There are
drives with hardware based encryption that also encrypt the MBR or UEFI
partitions. These are proprietary and therefore the source code can not
be audited by independent security professionals. For this reason we
will not be discussing hardware encrypted drives.

Since Linux is our OS of choice , we will be using LUKS: or Linux
Unified Key setup. [LUKS](https://en.wikipedia.org/wiki/Linux_Unified_Key_Setup) is based on an enhanced version of [cryptsetup](https://en.wikipedia.org/wiki/Dm-crypt#cryptsetup),
using [dm-crypt](https://en.wikipedia.org/wiki/Dm-crypt) as the disk encryption backend. The next question is how
do we encrypt our OS. With most Linux distros you are given the option
to encrypt your system during installation. All you have to do is follow
the documentation for your given disrto and in most cases the OS
installer will guide you through the installation. The most that is
required of you is to put in the required information when prompted.
After you have completed the installation you should have a Linux Os
with full disk encryption

There is one very important thing you must know however. As mentioned
previously with full disk encryption the boot partition, or MBR is not
encrypted. This means that if a malicious user was to have physical
access to your computer, malicious code--like a [keylogger](https://en.wikipedia.org/wiki/Keystroke_logging)-- could be
installed on you [boot partition](https://en.wikipedia.org/wiki/System_partition_and_boot_partition). It only takes a few seconds for a USB
to be inserted into your laptop and a virus uploaded. It does not matter
if your computer is running or powered down, It is still just as
vulnerable. You are given some protection is you have a bios password
and you have configured your computer not to auto-mount external media.
I say "some protection" because there is no practical way to stop a
gifted attacker if they are committed to compromising your computer. The
only other way to prevent an attacker from doing this is to transfer you
boot partition to an external USB. This way if you remove the USB from
you computer no one will be able to boot it unless they use a live CD. I
hope you are starting to see a pattern hear and I'm going to say it
again: **There is no way to stop a gifted attacker if they are committed
to compromising your computer!!**

***


[☝](#toc)
### Passwords

We all use them, weather its signing in to our email accounts,signing
into Github, or unlocking our OS user account. Passwords are in our
lives and they are here to stay, but many don't take the time to think
about what goes into making a strong high password. Most people use a
password that's easy for them to remember like a pets name, a birthday,
or the name of one of their children. These are the passwords malicious
users want us to have. All a cracker has to do is search on Google to
find out all the personal information they need to know about someone to
gain access to their computer. So how do we prevent someone from
figuring out our password? Keep on reading and by the time we are done
you will know that and much more.

We are going to start of with some guidelines for making a strong
password.
* Use a minimum password length of 12 to 14 characters if permitted.
* Include lowercase and uppercase alphabetic characters, numbers and
  symbols if permitted.
* Generate passwords randomly where feasible.
* Avoid using the same password twice (e.g., across multiple user
  accounts and/or software systems).
* Avoid character repetition, keyboard patterns, dictionary words,
  letter or number sequences, usernames, relatives or pet names,
  romantic links (current or past) and biographical information (e.g.,
  ID numbers, ancestors' names or dates).
* Avoid using information that is or might become publicly associated
  with the you or the account.
* Avoid using information that your colleagues and/or acquaintances
  might know to be associated with the you.
* Avoid using a place of birth or names of educational facilities like a
  high school or university.
* Avoid using something related to a favorite sports team.
* Do not use the word "password"! Yes people use it all the time.
* Do not use passwords which consist wholly of any simple combination of
  the aforementioned weak components.
* Do not use the default password that came with your device or user
  account.
* **Do not write your password down on a piece of paper or sticky
  note!** If you do why bother making a strong password?

Now that we have some guidelines we can start working on our password.
As mentioned above password length is very important but we also want a
password with uppercase and lowercase letters, and it should have
numbers and special characters such as [ &*?@#: ]. We also want our
passwords to be as random as possible. Random passwords consist of a
string of symbols of specified length taken from some set of symbols
using a random selection process in which each symbol is equally likely
to be selected. The symbols can be individual characters from a
character set (e.g., the ASCII character set), syllables designed to
form pronounceable passwords, or even words from a word list (thus
forming a passphrase). Many users choose a password that is memorable,
however the easier a password is for the user to remember generally
means it will be easier for an attacker to guess. On the other hand
passwords which are difficult to remember may also reduce the security
of the system because (a) users may need to write down their password on
a sticky note, which in turn will end up affixed to their desktop or
computer monitor. (b) users are more likely to re-use the same password
for all of their accounts.

One of the better ways to create a strong password is to use memory
techniques. With [mnemonic](https://en.wikipedia.org/wiki/Mnemonic) passwords users develop memorable phrases and
use them to generate more or less random passwords which are
nevertheless relatively easy for the user to remember. For instance, the
first letter of each word in a memorable phrase. In the example we will
use a memorable phrase and use the first letter in each word as part of
our password.

     Example:  four red balls rolled down the hill and stopped at Jose's house    password: frbrdthasaJh

This password is easy to remember but it does not have numbers or
special characters. Another way to make mnemonic passwords is called
after-the-fact mnemonics: After the password has been established,
invent a mnemonic phrase that fits. It does not have to be reasonable or
sensible, only memorable. This allows passwords to be random. So If you
created the password [ 7paHjolT? ] a possible mnemonic would be 'seven
people and Horses jump over lost Trees? ' .

Another way to create strong passwords is to combine mnemonic with
phonetic pronunciation. Phonetic pronunciation is means how something
sounds. Instead of writing what you see [e.g , at , and , four ] we are
going to type how it sounds (e.g [ate = 8] [at = @] [and = & ] [four =

1. . Obviously we can't do this for every word but it is useful for some
   phrases . In the next example we will use the phrase from earlier.

   Example: four red balls rolled down the hill and stopped at Jose's
   house password: 4rbrdth&s@Jh

As you can see the password now has upper and lower case letters,
numbers and special characters. Although it is a little bit shorter than
what is recommended it is still a fairly strong password and easy to
remember. There are however other ways we can make our passwords
stronger.

We have gone over mnemonic and phonetic password and there is another
great way to make strong passwords. This time we are we are going to
combine everything we have learned and have a little fun at the same
time. What we are going to do is make up a funny story. It can be
anything you want it to be and it does not have to make any sense.
Actually the less sense the story makes the better. We want to have a
password with at least 12-14 characters, upper and lower case letters
and numbers. In the next example we will make a password then make up a
memorable phrase to associate with the password. Remember to use
phonetic pronunciation.

     Example 1)  cH9`b8L^aydS|   camels Have nine backticks but ate Long carrots are yummy dogs smoke pipes 

I'm sure you are thinking "How the heck could I remember that?" You have
to remember we all think differently. A password I created may be
difficult for you to remember and vise versa. The way my mind associates
things is unique. That story makes no sense but is easy for me to
remember. You can also use this method to create a password over the
course of a week. On day one create a 4-5 character "base password ",
then add 2-3 characters every day until you are satisfied with the
strength of the password Keep in mind once you make a memorize a strong
password you can make it stronger over time. Every week you can add a 1
character or even 2.

[☝](#toc)
#### Security implications passwords:
Even the strongest passwords allow us no
protection if they are compromised. When in public be cognizant of your
surrounding. Are you in view of any security cameras that could be
recording you type in your password? Be aware of shoulder surfers that
may be watching you unlock your notebook or log into online accounts.

[☝](#toc)
### Password Managers

Another tool that can be helpful is a password manger. A password manger
is a encrypted data base that assists in generating, storing, and
retrieving complex passwords. The user must create a master password
and/or [keyfile](https://en.wikipedia.org/wiki/Mnemonic) to unlock the data base. Many of these managers also have
password generators. These are simple to operate and allow users to
generate strong passwords or keyfiles in seconds. One of the biggest
advantages of a password manager is it eliminates the need to remember
multiple password for different logins. Users are also no longer
compelled to reuse the same password for multiple sites.

Generally there are 2 different types of password managers

[☝](#toc)
#### Locally-installed password managers
Commonly reside on the user's
personal computer or mobile device, such as smart phones, in the form of
a locally-installed software application. These applications can be
offline, wherein the password database is stored independently and
locally on the same device as the password manager software.
Alternatively, password managers may offer or require a cloud-based
approach, wherein the password database is dependent on an online file
hosting service and stored remotely, but handled by password management
software installed on the user's device.

[☝](#toc)
#### Web-based password managers
 An online password manager is a website that securely
stores login details. They are a web-based version of more conventional
desktop-based password manager. The advantages of online password
managers over desktop-based versions are portability (they can generally
be used on any computer with a web browser and a network connection,
without having to install software), and a reduced risk of losing
passwords through theft from or damage to a single PC - also the same
risk is present for the server that is used to store the users passwords
on. In both cases this risk can be prevented by ensuring secure backups
are taken.The major disadvantages of online password managers are the
requirements that the user trusts the hosting site.

[☝](#toc)
##### Security implications password managers
Its important to keep in mind the security of
your password manager depends on the strength of the chosen master
password (which might be guessed or brute-forced) and keyfile if one is
used. Care must be taken that the passphrase itself is never stored
locally where a malicious program or individual could read it: nor
should you leave a USB with your keyfile in an unsecured location were
it can be lost or stolen. A compromised master password will render all
of the protected passwords vulnerable if you don not also use a keyfile.
Just because you use both password and keyfile does not make a password
manager infallible. As with any system which involves the user entering
a password, the master password may also be attacked and discovered
using a key-logger. Some password managers attempt to use virtual
keyboards to reduce this risk - though this again is vulnerable to key
loggers which take screenshots as data is entered. This risk can be
mitigated with the use of a [multi-factor authentication device](https://en.wikipedia.org/wiki/Multi-factor_authentication) such as a keyfile .

[☝](#toc)
### Man in the middle attacks

A man-in-the-middle attack (MITM) is an attack where the attacker
secretly relays and possibly alters the communication between two
parties who believe they are directly communicating with one other. An
example of a man-in-the-middle attack is active eavesdropping, in which
the attacker makes independent connections with the victims and relays
messages between them to make them believe they are talking directly to
each other over a private connection, when in fact the entire
conversation is controlled by the attacker. The attacker must be able to
intercept all relevant messages passing between the two victims and
inject new ones. This is straightforward in many circumstances; for
example, an attacker within reception range of wireless access point can
insert himself as a man-in-the-middle.

As an attack that aims at circumventing mutual authentication, or lack
thereof, a man-in-the-middle attack can succeed only when the attacker
can impersonate each endpoint to their satisfaction as expected from the
legitimate end. All protocols include some form of endpoint
authentication specifically to prevent attacks. For example,
authentication forwarded to either one or two parties using a mutually
trusted certificate of authority.

Example:

     Suppose Bob wishes to communicate with Alice. Meanwhile, Mallory wishes to intercept the  
     conversation to eavesdrop and optionally to deliver a false message to Bob.

     First, Alice asks Bob for his public key. If Bob sends his public key to Alice, but Mallory
     is able to intercept it, a man-in-the-middle attack can begin.

     Mallory sends a forged message to Alice that purports to come from Bob, but instead includes 
     Mallory's public key.

     Alice, believing this public key is Bob's, encrypts her message with Mallory's key and
     sends the encrypted message back to Bob.
    
     Mallory again intercepts, decrypts the message using her private key, possibly alters
     it if she wants, and re-encryptes  it using the public key Bob originally sent to Alice.
     
     When Bob receives the newly encrypted message he believes it came from Alice.

[☝](#toc)
#### Defense and Detection MITM attacks
They are largely detected, or
prevented by two means: authentication, and tamper detection.
Authentication provides some degree of certainty that a given message
has come from a source. Means of tamper detection, by comparison, merely
shows evidence that a message may have been altered, rather than
providing any guarantees.

[☝](#toc)
### Authentication
 All systems that are secure against MITM attacks
provide some method of authentication for messages. Most require an
exchange of information (such as public keys) in addition to the message
over a [secure channel](https://en.wikipedia.org/wiki/Secure_channel). Such protocols often use key-agreement protocols
have been developed, with different security requirements for the secure
channel, though some have attempted to remove the requirement for any
secure channel at all.

A [public key infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure), such as [transport layer security](https://en.wikipedia.org/wiki/Transport_Layer_Security), may
harden [Transmition Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) against Man-in-the-middle-attacks.
In such structures, clients and servers exchange certificates which are
issued and verified by a trusted third party called a [certificate authority](https://en.wikipedia.org/wiki/Certificate_authority) (CA). If the original key to authenticate this CA has not been
itself the subject of a MITM attack, then the certificates issued by the
CA may be used to authenticate the messages sent by the owner of that
certificate.

[☝](#toc)
### Tamper detection
 [Latency](https://en.wikipedia.org/wiki/CAS_latency) examination can potentially detect the
attack in certain situations,[8] such as with long calculations that
lead into tens of seconds like hash functions. To detect potential
attacks, parties check for discrepancies in response times. For example:
Say that two parties normally take a certain amount of time to perform a
particular transaction. If one transaction, however, were to take an
abnormal length of time to reach the other party, this could be
indicative of a third party's interference inserting additional latency
in the transaction.

[☝](#toc)
### Cryptocurrency Wallets

#### Software Wallets

Local wallets are installed on your computer or mobile
device/smart-phone and provide the user with complete control over the
wallet. They also enable the user to create a wallet address for sending
and receiving digital currency. The main benefit of using a local wallet
is the user maintains complete control of the private keys.

Web-based wallets store your private keys online, on a server controlled
by someone else and connected to the Internet. An advantage of web-based
wallets is that you can access them from anywhere, regardless of which
device you are using. However, they also have one major disadvantage:
unless implemented correctly, they can put the organization running the
website in charge of your private keys – essentially taking your digital
currency out of your control.

Guidelines for keeping your wallet secure:

* One way to protect your wallet from prying eyes is to encrypt it with
  a strong password. This makes it difficult to access your wallet, but
  not impossible. If your computer is compromised by malware, malicious
  users could log your keystrokes to find your password.
* If you have your private keys stored in one wallet, but you mislay
  that wallet or it gets corrupted, you will lose your keys. Backing up
  your wallet makes a copy of your private keys, but it's important to
  back up your whole wallet. Some addresses are used to store change
  from transactions, and may not be shown to you by default. Back up the
  whole wallet in several different places, and keep them safe from
  prying eyes. *Use multisig when possible. Multi-signature addresses
  allow multiple parties to partially seed an address with a public key.
  When someone wants to spend some of the digital currency, they need
  some of these people to sign their transaction in addition to
  themselves. The required number of signatures is agreed at the start
  when people create the address.
* If you are too nervous to store your private keys digitally, for fear
  that they may be stolen by malicious users, there is another option:
  ‘cold storage’. Cold storage wallets store private bitcoin keys
  offline, so that they can’t be stolen by someone else on the Internet.

[☝](#toc)
#### Hardware Wallets

To date there have been no verifiable incidents of digital currency
stolen from hardware wallets. Hardware wallets are relatively new, but
at least for the time being they have maintained a good track record,
unlike the numerous incidents of digital currency theft from
Internet-connected computers. Although there have been no verifiable
thefts of digital currency from hardware wallets does not make the user
immune to other treats. Becoming the victim of a Man In The Middle
attack, sending your digital currency to the wrong address, losing your
hardware wallet and losing your digital currency mnemonic recovery
passphrase are some of the way you can still permanently lose you
digital currency.

[☝](#toc)
#### Mnemonic Recovery Passphrase

Mnemonic recovery passphrases are used to recover your digital currency
if (a) you lose your wallet login information (b) your computer or
hardware wallet is lost or stolen (c) the data on you hardware wallet or
computer is corrupted. The mnemonic passphrase is provided to you when
you sign up for a new blockchain wallet. It will be impossible to
recover your digital currency with out it. These guidelines will help
you keep your Mnemonic passphrase safe and secure.
* When it is first displayed during wallet creatioin write it down
  legibly and at the top of the paper write what the passphrase if for.
* Store it in a secure place like a safe, fire-proof security box or a
  locked draw in your desk that only you have the key for.
* Never store it on a computer or smart-phone even if you use a password
  manager. If a malicious user compromises your computer all all he/she
  has to do is install a keylogger to obtain all of your passwords.
* Avoid taking your mnemonic with you when leaving your flat to go out
  in public. If you lose it you will not be able to recover you digital
  currency in that wallet.
* If you lose your mnemonic, create a new wallet immediately and
  transfer everything to your new wallet. Why take a chance?
* To help prevent losing or damaging your mnemonic you can store it on
  [Cryptosteel](http://cryptosteel.com/).

[☝](#toc)
### Afterword

Using best security practices will not be helpful if only used when its
convenient for you or when you remember to use them. IT security should
be factored into every decision you make. At first it can be frustrating
and time consuming but it will become second nature to you over time.
Good Luck!!


| No | Type                | Source                                                                                   |
|:---|:--------------------|:-----------------------------------------------------------------------------------------
| 1  | doc                 | [Brainwallet 0Brand](æternity-wiki-authors#0brand)                                       
| 2  | doc                 | [Brainwallet zwilla](æternity-wiki-authors#zwilla)
| 3  | doc                 | [Brainwallet oldpaul](æternity-wiki-authors#odpaul)
| 4  | doc                 | [Brainwallet snasps](æternity-wiki-authors#snasps)
| 5  | open-source model   | [open-source_wiki](https://en.wikipedia.org/wiki/Open-source_model)                      
| 6  | closed-source model | [proprietary-software_wiki](https://en.wikipedia.org/wiki/Proprietary_software)          
| 7  | Debian OS           | [**Debian** The Universal Operating System](https://www.debian.org/)                     
| 8  | Qubes OS            | [Qubes OS_wiki](https://en.wikipedia.org/wiki/Qubes_OS)                                  
| 9  | Qubes OS            | [**Qubes OS**: A reasonably secure operating system](https://qubes-os.org)               
| 10 | Whonix              | [**Whonix OS**; privacy, security, & anonymity on the internet](https://whonix.org)      
| 11 | Tails OS            | [**Tails OS**:  Privacy for anyone anywhere](https://tails.boum.org/)                    
| 12 | passwords           | [Passwords_wiki](https://en.wikipedia.org/wiki/Password)                                 
| 11 | password strength   | [Password strength_wiki](https://en.wikipedia.org/wiki/Password_strength)                
| 12 | MITM Attacks        | [**Tor Project**: Anonymity Online](https://www.torproject.org/)                         
| 13 | MITM Attacks        | [Man in the middle attacks_wiki](https://en.wikipedia.org/wiki/Man-in-the-middle_attack) 


## Additional WARNINGS

THIS INFORMATION AND INSTRUCTIONS ARE PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THIS INSTRUCTIONS OR THE USE OR OTHER
DEALINGS IN THE INFORMATION INSTRUCTIONS.

DO NOT SHARE YOUR PRIVATE KEYS!!!

[☝](#toc)
[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#toc)

<a href="https://aeternity.slack.com/"><img
src="https://slack.global.ssl.fastly.net/272a/img/icons/favicon-32.png"><sup>join
us at slack</sup></a>