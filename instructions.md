1. Clone the dsl branch of repository by doing `git clone --single-branch -b dsl https://github.com/denizsokmen/dsl-ac68u.git`
2. Clone am-toolchains with `git clone https://github.com/RMerl/am-toolchains.git`
3. Follow instructions here to download all needed libraries (follow just the apt-get part)
4. Navigate to `~/dsl-ac68u/release/src-rt-6.x.4708/` and delete the toolchains symlink file/folder
5. Follow instructions here to configure BCM-SDK (change ~/asuswrt-merlin.382/with the name of the folder cloned at point n.1)
6. Navigate to `~/dsl-ac68u/release/src/router/shared/prebuild` and copy-paste the RT-AC68U folder into the same directory and rename the new folder to DSL-AC68U
7. Navigate to `~/dsl-ac68u/release/src/router/rc/prebuild` and copy-paste the RT-AC68U folder into the same directory and rename the new folder to DSL-AC68U
8. Navigate to `~/dsl-ac68u/release/src/router/httpd/prebuild` and copy-paste the RT-AC68U folder into the same directory and rename the new folder to DSL-AC68U
9. Navigate to `~/dsl-ac68u/release/src/router/libevent-2.0.21/test/` and edit the Makefile.am file. Replace all occurrences of $(top_srcdir) with `~/dsl-ac68u/release/src/router/libevent-2.0.21` (this was necessary for me to prevent file-not-found errors while compiling caused by the bad variable)
10. Download the DSL-AC68U source from here
11. Extract the archive, then extract GPL_DSL-AC68U tar. Navigate to the extracted folder into `./release/src/router/rc/prebuild` and copy all files files into `~/dsl-ac68u/release/src/router/rc/prebuild/DSL-AC68` folder (replacing the original files).
12. Navigate to the extracted folder into `./release/src-rt-6.x.4708/` and copy tc_fw folder to `~/dsl-ac68u/release/src-rt-6.x.4708/`
13. Navigate to `~/dsl-ac68u/release/src/router/wget/` and run `autoreconf -fi` (this was necessary for me to fix a wget compile error)
14. Navigate to `~/dsl-ac68u/release/src/router/wget/po/`  and open the file file Makefile.in.in. I had to change GETTEXT_MACRO_VERSION from 0.18 to 0.19 as I was getting errors while compiling (but that may depend on my setup).
15. Navigate to `~/dsl-ac68u/release/src/router/tor/` and run `autoreconf -fi` (this was necessary for me to fix a wget compile error)
16. Navigate to `./release/src-rt-6.x.4708/` and type make clean followed by make dsl-ac68u to start the compile process.
17. At the end, if everything went smooth you should have the DSL-AC68U_384.7_alpha1_DSL_1.0.4.6.trx image into `~/dsl-ac68u/release/src-rt-6.x.4708/image/`
