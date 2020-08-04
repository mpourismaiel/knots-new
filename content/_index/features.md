+++
fragment = "content"
weight = 30

title = "Enhancement sets"
subtitle = "Features that will be available in the next release of Bitcoin Core are highlighted in green."
+++

<br>

### Packaging cleanups ("syslibs")

<br>

Adds options to build using system LevelDB, libsecp256k1, and UniValue libraries, and/or without protobuf (see `./configure --help` for usage).

Please note this may be dangerous and make theft from you possible if used with versions of the LevelDB or libsecp256k1 libraries which have not been audited to meet the bug-for-bug compatibility required by Bitcoin's consensus protocol. These options are disabled by default for this reason.

It also adds options to disable building bitcoin-cli or bitcoin-tx individually, and avoids involving foreign git trees in the build.

See also:

- Support for building against system LevelDB [[2241](https://github.com/bitcoin/bitcoin/pull/2241)]
- configure: Add unsupported --with-system-libsecp256k1 configure flag [[5416](https://github.com/bitcoin/bitcoin/pull/5416)]
- configure: BITCOIN_SUBDIR_TO_INCLUDE: Improve compatibility with paths including space and multiline cpp output [[5872](https://github.com/bitcoin/bitcoin/pull/5872)]
- Use system univalue by default [[7485](https://github.com/bitcoin/bitcoin/pull/7485)]
- crypto/sha256: Use pragmas to enforce necessary intrinsics for GCC and Clang [[13789](https://github.com/bitcoin/bitcoin/pull/13789)]
- test: Support -cli tests using external bitcoin-cli [[15155](https://github.com/bitcoin/bitcoin/pull/15155)]
- test: Always define the raii_event_tests test suite [[16564](https://github.com/bitcoin/bitcoin/pull/16564)]
- util: Add missing headers to util/fees.cpp [[17450](https://github.com/bitcoin/bitcoin/pull/17450)]
- Unbreak build with Boost 1.72.0 [[17654](https://github.com/bitcoin/bitcoin/pull/17654)]
- configure: Check assembler crc32 with user CXXFLAGS appended [[#bbeb227](https://github.com/bitcoinknots/bitcoin/commit/bbeb2278e09827fa14ab22200bcae630a6ed03a2)]

---

### Functional and policy enhancements

<br>

This is a collection of fixes, and various other improvements:

- Parse URIs with non-BTC amounts [[553](https://github.com/bitcoin/bitcoin/pull/553)]
- -acceptnonstdtxn option to skip "non-standard transaction" checks [[559](https://github.com/bitcoin/bitcoin/pull/559)]
- Support for Tonal Bitcoin units (ᵇTBC, ˢTBC, and TBC) [[929](https://github.com/bitcoin/bitcoin/pull/929)]
- Restore ability to display addresses in GUI [[5861](https://github.com/bitcoin/bitcoin/pull/5861)]
- [Qt] support for persisted rpc console history [[5891](https://github.com/bitcoin/bitcoin/pull/5891)]
- Qt: Add network port input box to GUI settings [[7107](https://github.com/bitcoin/bitcoin/pull/7107)]
- Make RBF policies optional [[7219](https://github.com/bitcoin/bitcoin/pull/7219)]
- Render icons from SVG [[7483](https://github.com/bitcoin/bitcoin/pull/7483)]
- RPC: sendrawtransaction: Allow the user to ignore/override specific rejections [[7533](https://github.com/bitcoin/bitcoin/pull/7533)]
- Add mempool statistics collector [[8501](https://github.com/bitcoin/bitcoin/pull/8501)]
- [Qt] Add interactive mempool graph [[8550](https://github.com/bitcoin/bitcoin/pull/8550)]
- RPC: Add parameter to addmultisigaddress / createmultisig to sort public keys [[8751](https://github.com/bitcoin/bitcoin/pull/8751)]
- Wallet/RPC: sweepprivkeys method to scan UTXO set and send to local wallet [[9152](https://github.com/bitcoin/bitcoin/pull/9152)]
- Drop IO priority to idle while reading blocks for getblock requests [[9245](https://github.com/bitcoin/bitcoin/pull/9245)]
- Refactor mempool.dat to be extensible, and store missing info [[9422](https://github.com/bitcoin/bitcoin/pull/9422)]
- [RPC] dumpmasterprivkey command [[9504](https://github.com/bitcoin/bitcoin/pull/9504)]
- rpc: Don't FlushStateToDisk when pruneblockchain(0) [[9524](https://github.com/bitcoin/bitcoin/pull/9524)]
- If -spkreuse=0, ensure transactions in mempool always have unique scriptPubKeys [[9749](https://github.com/bitcoin/bitcoin/pull/9749)]
- Qt: Network Watch tool [[9849](https://github.com/bitcoin/bitcoin/pull/9849)]
- Expire bitcoind &amp; bitcoin-qt 1-2 years after its last change [[10282](https://github.com/bitcoin/bitcoin/pull/10282)]
- Added support for MSG_FILTERED_WITNESS_BLOCK messages. [[10350](https://github.com/bitcoin/bitcoin/pull/10350)]
- ZMQ: add publishers for wallet transactions. [[10554](https://github.com/bitcoin/bitcoin/pull/10554)]
- Relax punishment for peers relaying invalid blocks and headers [[10593](https://github.com/bitcoin/bitcoin/pull/10593)]
- Bugfix: net: Apply whitelisting criteria to outgoing connections [[10594](https://github.com/bitcoin/bitcoin/pull/10594)]
- RPC: Allow rpcauth configs to specify a 4th parameter naming a specific wallet (multiwallet RPC support) [[10615](https://github.com/bitcoin/bitcoin/pull/10615)]
- Escape rather than remove any printable characters in UAs [[10731](https://github.com/bitcoin/bitcoin/pull/10731)]
- Add new bitcoin_rw.conf file that is used for settings modified by this software itself [[11082](https://github.com/bitcoin/bitcoin/pull/11082)]
- [wallet] [rpc] sendtoaddress/sendmany: Add explicit feerate option [[11413](https://github.com/bitcoin/bitcoin/pull/11413)]
- Multiselect in coincontrol treewidget and display selected count [[11750](https://github.com/bitcoin/bitcoin/pull/11750)]
- Bugfix: RPC/Wallet: Include HD key metadata in dumpwallet [[11803](https://github.com/bitcoin/bitcoin/pull/11803)]
- Wallet: Support disabling implicit Segwit operation [[12146](https://github.com/bitcoin/bitcoin/pull/12146)]
- RPC: Support addnode onetry without making the connection priviliged [[12674](https://github.com/bitcoin/bitcoin/pull/12674)]
- RPC: Add ancestor{count,size,fees} to listunspent output [[12677](https://github.com/bitcoin/bitcoin/pull/12677)]
- Add RPC Whitelist Feature [[12763](https://github.com/bitcoin/bitcoin/pull/12763)]
- wallet: Show fee in results for signrawtransaction* when known [[12911](https://github.com/bitcoin/bitcoin/pull/12911)]
- Add RPC call setscriptthreadsenabled: allow to temp. throttle CPU usage [[12965](https://github.com/bitcoin/bitcoin/pull/12965)]
- Add POWER8 ASM for 4-way SHA256 [[13203](https://github.com/bitcoin/bitcoin/pull/13203)]
- wallet: Replace %w by wallet name in -walletnotify script [[13339](https://github.com/bitcoin/bitcoin/pull/13339)]
- bitcoin-tx: Require that input amount is provided for witness transactions [[13608](https://github.com/bitcoin/bitcoin/pull/13608)]
- gitian-linux: Build binaries for 64-bit POWER [[14066](https://github.com/bitcoin/bitcoin/pull/14066)]
- gui: Add Windows taskbar progress [[14137](https://github.com/bitcoin/bitcoin/pull/14137)]
- Try to use posix_fadvise with CBufferedFile [[14485](https://github.com/bitcoin/bitcoin/pull/14485)]
- Fix possible data race when committing block files [[14501](https://github.com/bitcoin/bitcoin/pull/14501)]
- rpc: Add min_conf option to fund transaction calls [[14641](https://github.com/bitcoin/bitcoin/pull/14641)]
- zmq: enable tcp keepalive [[14687](https://github.com/bitcoin/bitcoin/pull/14687)]
- http: Fail initialization when any bind fails [[14968](https://github.com/bitcoin/bitcoin/pull/14968)]
- GUI: Restore RPC Console to non-wallet tray icon menu [[15023](https://github.com/bitcoin/bitcoin/pull/15023)]
- gui: don't disable the sync overlay when wallet is disabled [[15084](https://github.com/bitcoin/bitcoin/pull/15084)]
- fix getentropy import check on osx [[15103](https://github.com/bitcoin/bitcoin/pull/15103)]
- GUI: Replace send-to-self with dual send+receive entries [[15115](https://github.com/bitcoin/bitcoin/pull/15115)]
- validation: Flush state after initial sync [[15218](https://github.com/bitcoin/bitcoin/pull/15218)]
- feature: Added ability for users to add a startup command [[15367](https://github.com/bitcoin/bitcoin/pull/15367)]
- torcontrol: Query Tor for correct -onion configuration [[15423](https://github.com/bitcoin/bitcoin/pull/15423)]
- GUI: Add Pairing tab with Tor onion address as copyable text and QR code [[15428](https://github.com/bitcoin/bitcoin/pull/15428)]
- Ignore BIP-152 HB requests from non-witness peers [[15633](https://github.com/bitcoin/bitcoin/pull/15633)]
- Move Win32 defines to configure.ac to ensure they are globally defined [[15704](https://github.com/bitcoin/bitcoin/pull/15704)]
- gui: Add shortcuts for tab tools [[15756](https://github.com/bitcoin/bitcoin/pull/15756)]
- gui: Add close window shortcut [[15768](https://github.com/bitcoin/bitcoin/pull/15768)]
- Add feerate histogram to getmempoolinfo [[15836](https://github.com/bitcoin/bitcoin/pull/15836)]
- Restore warning for individual unknown version bits, as well as unknown version schemas [[15861](https://github.com/bitcoin/bitcoin/pull/15861)]
- QA: Add wallet_implicitsegwit to test the ability to transform keys between address types [[15888](https://github.com/bitcoin/bitcoin/pull/15888)]
- Wallet, GUI: Warn when sending to already-used Bitcoin addresses [[15987](https://github.com/bitcoin/bitcoin/pull/15987)]
- transaction fees in getblock [[16083](https://github.com/bitcoin/bitcoin/pull/16083)]
- qt: Add privacy to the Overview page [[16432](https://github.com/bitcoin/bitcoin/pull/16432)]
- Serve BIP 157 compact filters [[16442](https://github.com/bitcoin/bitcoin/pull/16442)]
- Dump transaction version as an unsigned integer in RPC/TxToUniv [[16525](https://github.com/bitcoin/bitcoin/pull/16525)]
- rpc: have raw transaction decoding infer output descriptors [[16795](https://github.com/bitcoin/bitcoin/pull/16795)]
- Let validateaddress locate error in Bech32 address [[16807](https://github.com/bitcoin/bitcoin/pull/16807)]
- gui: create PSBT with watch-only wallet [[16944](https://github.com/bitcoin/bitcoin/pull/16944)]
- gui: Change sendcoins dialogue Yes to Send [[16964](https://github.com/bitcoin/bitcoin/pull/16964)]
- Bip174 extensions [[17034](https://github.com/bitcoin/bitcoin/pull/17034)]
- descriptors: Introduce sortedmulti descriptor [[17056](https://github.com/bitcoin/bitcoin/pull/17056)]
- gui: Add toolTip and placeholderText to sign message fields [[17125](https://github.com/bitcoin/bitcoin/pull/17125)]
- gui: Improved tooltip for send amount field [[17180](https://github.com/bitcoin/bitcoin/pull/17180)]
- gui: Add placeholder text to the sign message field [[17186](https://github.com/bitcoin/bitcoin/pull/17186)]
- gui: send amount placeholder value [[17195](https://github.com/bitcoin/bitcoin/pull/17195)]
- wallet: Do not turn OP_1NEGATE in scriptSig into 0x0181 in signing code [[17204](https://github.com/bitcoin/bitcoin/pull/17204)]
- Fix issue with conflicted mempool tx in listsinceblock [[17258](https://github.com/bitcoin/bitcoin/pull/17258)]
- gui: Improve "Hide" button tool-tip message [[17360](https://github.com/bitcoin/bitcoin/pull/17360)]
- ci: Travis support for PowerPC64 [[17402](https://github.com/bitcoin/bitcoin/pull/17402)]
- qt: Fix missing qRegisterMetaType for size_t [[17427](https://github.com/bitcoin/bitcoin/pull/17427)]
- rpc: Expose block height of wallet transactions [[17437](https://github.com/bitcoin/bitcoin/pull/17437)]
- Bugfix: GUI: Recognise NETWORK_LIMITED in formatServicesStr [[17474](https://github.com/bitcoin/bitcoin/pull/17474)]
- psbt: handle unspendable psbts [[17524](https://github.com/bitcoin/bitcoin/pull/17524)]
- gui: show watch-only balance in send screen [[17587](https://github.com/bitcoin/bitcoin/pull/17587)]
- IsUsedDestination should count any known single-key address [[17621](https://github.com/bitcoin/bitcoin/pull/17621)]
- Expose block filters over REST [[17631](https://github.com/bitcoin/bitcoin/pull/17631)]
- qt: Add -guisettingsdir option [[17636](https://github.com/bitcoin/bitcoin/pull/17636)]
- wallet: Fix origfee return for bumpfee with feerate arg [[17643](https://github.com/bitcoin/bitcoin/pull/17643)]
- rpc: require second argument only for scantxoutset start action [[17728](https://github.com/bitcoin/bitcoin/pull/17728)]
- net: Log to net category for exceptions in ProcessMessages [[17762](https://github.com/bitcoin/bitcoin/pull/17762)]
- gui: Shortcut to close RPC Console [[17795](https://github.com/bitcoin/bitcoin/pull/17795)]
- net: Use log categories when logging events that P2P peers can trigger arbitrarily [[17828](https://github.com/bitcoin/bitcoin/pull/17828)]
- Fix GBT: Restore "!segwit" and "csv" to "rules" key [[17946](https://github.com/bitcoin/bitcoin/pull/17946)]
- RPC/Wallet: Add "use_txids" to output of getaddressinfo [[#c05d6a8](https://github.com/bitcoinknots/bitcoin/commit/c05d6a801d797dae722892e0c2e90db9b00bdc19)]
- Restore original bytespersigop as bytespersigopstrict [[#a44c3b4](https://github.com/bitcoinknots/bitcoin/commit/a44c3b4a921cf04018a09b9f58dc3a45698c7b12)]
- Restore blockmaxsize option, allowing to limit mined blocks by byte size [[#7321911](https://github.com/bitcoinknots/bitcoin/commit/73219112fd4c01c830a088949dcd7df903fdbd8c)]
- RPC: add transaction hash to mempool entry output [[#74c3834](https://github.com/bitcoinknots/bitcoin/commit/74c383451579df09f8b6cddda806b5513352dfe5)]
- Wallet: Increase default confirmation target to 144 [[#f2e441f](https://github.com/bitcoinknots/bitcoin/commit/f2e441f237558e826286a5a2920a58089025071c)]
- Drop IO priority to idle while reading blocks for getblock requests (Windows support) [[#e93d5d2](https://github.com/bitcoinknots/bitcoin/commit/e93d5d2ce39a470b0d5575d17ed77af5b6e031c0)]
- Policy: Restore support for mining based on coin-age priority [[#8883f19](https://github.com/bitcoinknots/bitcoin/commit/8883f192d198e38750a1e32fd6f32143169cc14d)]
- Make most policy options configurable in GUI Options, and add "corepolicy" option to use Bitcoin Core defaults [[#291bc8d](https://github.com/bitcoinknots/bitcoin/commit/291bc8d0326172b1624c3bc72d3d359f92244341)]
- GUI: Restore "request payment" button text [[#3cf4f0e](https://github.com/bitcoinknots/bitcoin/commit/3cf4f0e4c797aa092d37f11d5dde30dbdab3583c)]
- p2p: Re-enable bloom filters by default [[#e4167f1](https://github.com/bitcoinknots/bitcoin/commit/e4167f15f230fcd74a21b985c016b7c238f92146)]
- Wallet: Preserve "key origin" flags in old wallets [[#7af5a0f](https://github.com/bitcoinknots/bitcoin/commit/7af5a0f1d66f6e1a5ae761773dee4f6d20b30aac)]
- Qt/Options: Expose peercfilters in GUI using rwconf [[#3f5fdf0](https://github.com/bitcoinknots/bitcoin/commit/3f5fdf052c6f749686b063f3a3932a0211e1a789)]
- Updated consensus checkpoints [[#eaec9c2](https://github.com/bitcoinknots/bitcoin/commit/eaec9c219a2fc78d3e68e6a145e7fc50f825bd85)]
