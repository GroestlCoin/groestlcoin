Groestlcoin integration/staging tree
=================================
Forked from Bitcoin reference wallet 0.8.6 on March 2014

Updated to Bitcoin reference wallet 0.11.0 on August 2015

Updated to Bitcoin reference wallet 0.13.3 on January 2017

Updated to Bitcoin reference wallet 0.16.0 on June 2018

Updated to Bitcoin reference wallet 0.16.3 on September 2018

Updated to Bitcoin reference wallet 0.17.2 on March 2019

Updated to Bitcoin reference wallet 0.18.2 on March 2020

Updated to Bitcoin reference wallet 0.19.1 on June 2020

Updated to Bitcoin reference wallet 0.20.1 on September 2020

Updated to Bitcoin reference wallet 0.21.0 on December 2020

Groestlcoin Core Wallet

https://www.groestlcoin.org

The algorithm was written as a candidate for sha3

https://bitcointalk.org/index.php?topic=525926.0

What is Groestlcoin?
-----------------

Groestlcoin is an experimental new digital currency that enables instant payments to
anyone, anywhere in the world. Groestlcoin uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. Groestlcoin Core is the name of open source
software which enables the use of this currency.

For more information, as well as an immediately useable, binary version of
the Groestlcoin Core software, see https://www.groestlcoin.org/download.

License
-------

Groestlcoin Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see http://opensource.org/licenses/MIT.

Development Process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Groestlcoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions or are controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/groestlcoin/groestlcoin/tags) are created
regularly to indicate new official, stable release versions of Groestlcoin.

Development tips and tricks
---------------------------

**compiling for debugging**

Run configure with the --enable-debug option, then make. Or run configure with
CXXFLAGS="-g -ggdb -O0" or whatever debug flags you need.

**debug.log**

If the code is behaving strangely, take a look in the debug.log file in the data directory;
error and debugging message are written there.

The -debug=... command-line option controls debugging; running with just -debug will turn
on all categories (and give you a very large debug.log file).

The Qt code routes qDebug() output to debug.log under category "qt": run with -debug=qt
to see it.

**testnet and regtest modes**

Run with the -testnet option to run with "play groestlcoins" on the test network, if you
are testing multi-machine code that needs to operate across the internet.

If you are testing something that can run on one machine, run with the -regtest option.
In regression test mode blocks can be created on-demand; see qa/rpc-tests/ for tests
that run in -regest mode.

**DEBUG_LOCKORDER**

Groestlcoin Core is a multithreaded application, and deadlocks or other multithreading bugs
can be very difficult to track down. Compiling with -DDEBUG_LOCKORDER (configure
CXXFLAGS="-DDEBUG_LOCKORDER -g") inserts run-time checks to keep track of what locks
are held, and adds warning to the debug.log file if inconsistencies are detected.
