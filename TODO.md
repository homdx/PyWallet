# TODO

 * other way to broadcast transaction:
   * https://etherscan.io/pushTx
   * https://github.com/corpetty/py-etherscan-api
   * https://github.com/Marto32/pyetherscan
 * Test
   * use the test net
     * talking to nodes
     * via Etherscan https://ropsten.etherscan.io/apis
   * pylint
   * unit test account creation with different iterations
 * Automate / Document dev requirements
   * Automate VM or Docker
   * https://developer.android.com/studio/run/device.html
   * https://stackoverflow.com/a/5510745/185510
   * https://buildozer.readthedocs.io/en/latest/installation.html
   * https://kivy.org/docs/guide/packaging-android.html#packaging-your-application-into-apk
   * https://python-for-android.readthedocs.io/en/latest/quickstart/#installing-dependencies
   * https://kivy.org/docs/guide/packaging-android.html
   * Upstream
     * pydevp2p
       * fix broken tests:
         * https://github.com/ethereum/pydevp2p/commit/8e1f2b2ef28ecba22bf27eac346bfa7007eaf0fe
     * pyethereum
       * take a look at the potential unlock wallet performance improvement:
         https://github.com/ethereum/pyethereum/pull/777
     * python-for-android
       * recipes
         * secp256k1
           * `env['CFLAGS'] += ' -I' + join(libsecp256k1_dir, 'include')` # note the `+=`
           * `env['INCLUDE_DIR'] = join(libsecp256k1_dir, 'include')` # see secp256k1-py README.md
           * `env['LIB_DIR'] = join(libsecp256k1_dir, '.libs')` # see secp256k1-py README.md
           * `env['LDFLAGS'] += ' -L' + join(libsecp256k1_dir, '.libs')` # note the `.libs`
           * But in fact passing the library path ("LIB_DIR" and "LDFLAGS") may not be required
             because libsecp256k1 recipe has `self.install_libs(arch, *libs)`
         * libsecp256k1
           * remove java symbols from libsecp256k1 (configure `--enable-jni=no`) to reduce library size
           * `should_build()` with `.libs/libsecp256k1.so` check
      * Continuous integration
        * https://github.com/kivy/python-for-android/issues/625
        * p4a apk --reauirements=kivy --private /tmp/p4a/ --package=org.package.testname --name=testname --boostrap=sdl2
        * buildozer android p4a -- apk ...
 * MISC
   * kill running threads on application leave
     so it doesn't hangs when you quite while the thread tries to connect
