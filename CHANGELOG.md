# Changelog

## Unreleased

### Added

- `webcmd setup --mode local --browser chrome` detects and reuses an installed normal Google Chrome with an isolated `~/.webcmd/chrome/profiles` directory.
- Hosted mode can negotiate and run core validation, diagnostics, adapter lifecycle, profile lifecycle, and catalog-list commands advertised by Webcmd Cloud.
- `@agentrhq/webcmd/adapter-analysis` exposes platform-neutral validation and convention-audit rules for trusted hosted command inventories.
- `@agentrhq/webcmd/hosted/core-commands` exposes the `hosted-core-commands-v1` capability contract and canonical command IDs.
- `webcmd profile use` now stores a validated hosted profile preference locally.

### Changed

- Installed Google Chrome now uses a Webcmd-owned explicit nonzero loopback CDP port instead of Playwright's debugging pipe. Normal headed Chrome therefore retains its native `navigator.webdriver === false` value; Cloak, SLAB, and custom executables are unchanged.
- `WEBCMD_BROWSER_BINARY_PATH` can select a compatible Chromium executable for local browser Sessions; it takes precedence over the existing `CLOAKBROWSER_BINARY_PATH` override and isolates each browser build's profile data from managed Cloak profiles.
- Hosted help and completion advertise Cloud-owned core commands only when the authenticated manifest advertises them.
- Hosted command lists retain excluded commands as `LOCAL` rows and return a local-only error instead of plugin-install guidance.
- Local auth commands initialize user CLI compatibility shims, and hosted auth uses the same native grammar, flags, choices, and help as local mode.

## [0.8.2](https://github.com/AleksandLexy/webcmd/compare/webcmd-v0.8.4...webcmd-v0.8.2) (2026-11-11)


### ⚠ BREAKING CHANGES

* webcmd doctor now exits 78 on an unhealthy machine.
* **cli:** `webcmd browser fork` is removed. Use `webcmd adapter override <site>/<command>`.

### doctor

* exit CONFIG_ERROR when a required check fails ([#456](https://github.com/AleksandLexy/webcmd/issues/456)) ([eea4aba](https://github.com/AleksandLexy/webcmd/commit/eea4aba1bf28107ae37791a851e71594031fff64))


### Features

* add adapter override and hosted fixture export ([351f992](https://github.com/AleksandLexy/webcmd/commit/351f9926add8e9c40b2b157407b48df0831ac342))
* add Amazon India adapter ([7953914](https://github.com/AleksandLexy/webcmd/commit/7953914ea86bb5a1289848cefc637308fc5738a8))
* add Amazon India adapter ([beb1d17](https://github.com/AleksandLexy/webcmd/commit/beb1d17e755483efd5fd0d4fc59d6d93d0b3e681))
* add BMWBLOG read-only adapter ([#140](https://github.com/AleksandLexy/webcmd/issues/140)) ([41ae54a](https://github.com/AleksandLexy/webcmd/commit/41ae54a61781fa551498bbbeb6f7a526193e665e))
* add Claude Code plugin marketplace manifest ([#273](https://github.com/AleksandLexy/webcmd/issues/273)) ([5b17df0](https://github.com/AleksandLexy/webcmd/commit/5b17df048f91660766fafe43ba71fd0725e1ac30))
* add command tags and keywords ([ab35bdc](https://github.com/AleksandLexy/webcmd/commit/ab35bdc27b7f64fe5ab652d7f430d27467cfc21e))
* add grayscale color palette variables to root stylesheet ([d813a9d](https://github.com/AleksandLexy/webcmd/commit/d813a9da4e1472542b7a2fe0d8f27b4504ed95d3))
* add hosted builder profile commands ([e7a6040](https://github.com/AleksandLexy/webcmd/commit/e7a604025dcda54ab6e24a6b14bf10a14867214b))
* add Instagram, ChatGPT, Google Images, and Trip updates ([424de35](https://github.com/AleksandLexy/webcmd/commit/424de359e7b366527dbe9639ec4a6acc7474181a))
* add local auth handoff protocol ([b734485](https://github.com/AleksandLexy/webcmd/commit/b734485fd64322454fcc2a327aaa37fe572de0cd))
* add payment handoff to UPI QR scanner for District checkout and improve seat selection reliability ([765bd38](https://github.com/AleksandLexy/webcmd/commit/765bd38b087642bf43825d549285b511675f8cbf))
* add payment handoff to UPI QR scanner for District checkout and… ([3938f06](https://github.com/AleksandLexy/webcmd/commit/3938f06dfc5e6cbe324930e5a83af4f1632b3f96))
* add persistent session lease domain ([46747d0](https://github.com/AleksandLexy/webcmd/commit/46747d02fdfe8d465dfc76a0304917563465d2e5))
* add PyPI community plugin ([4a205b2](https://github.com/AleksandLexy/webcmd/commit/4a205b2acc07f5b96469638e351fd3469aa290e0))
* add PyPI community plugin ([93f6fbf](https://github.com/AleksandLexy/webcmd/commit/93f6fbf665c35da38edd6f8716e0b479ce831d09))
* add readable session identifiers ([#443](https://github.com/AleksandLexy/webcmd/issues/443)) ([dca5289](https://github.com/AleksandLexy/webcmd/commit/dca5289595b946ae77e4005c273a4469bebf5736))
* add skills add and remove commands ([1b0af7a](https://github.com/AleksandLexy/webcmd/commit/1b0af7ab792860d20f4b75ec486a6ba7abb12fed))
* add skills add and remove commands ([29b095d](https://github.com/AleksandLexy/webcmd/commit/29b095d7194c6ed74cc9787e4bea7fa557227569))
* add structured output to report and status built-ins ([18a3bed](https://github.com/AleksandLexy/webcmd/commit/18a3bed767c5c76112b0769f37dbb793641796f0))
* add structured output to report and status built-ins ([#306](https://github.com/AleksandLexy/webcmd/issues/306)) ([ce73083](https://github.com/AleksandLexy/webcmd/commit/ce73083c11dbb0d087ce95e9a022213f150d48c9))
* add support for local command execution in hosted mode ([52fd753](https://github.com/AleksandLexy/webcmd/commit/52fd753d56f7c5b47ed3d1b850fd52b09eed01b6))
* add the override provenance store and merge-base copies ([0bfafd8](https://github.com/AleksandLexy/webcmd/commit/0bfafd8adda6d5a50f2d265a97dded3bedb4f201))
* add tiered local web fetch ([8199dcb](https://github.com/AleksandLexy/webcmd/commit/8199dcb075463b63b214457a70908865011e0ad9))
* add webcmd adapter override to fork a plugin command with provenance ([8e509b4](https://github.com/AleksandLexy/webcmd/commit/8e509b463c2a6a7af9439b80d20426217da6dbc8))
* add Webcmd Codex plugin marketplace ([33395f0](https://github.com/AleksandLexy/webcmd/commit/33395f0f4349ee3b4e1abc11310045864ec15653))
* add webcmd update command ([3e228b1](https://github.com/AleksandLexy/webcmd/commit/3e228b143ca04fb9f0df5937fcbed183b2096867))
* add webcmd update command ([149c971](https://github.com/AleksandLexy/webcmd/commit/149c971c65853c4745ae82b107aab2bee461c794))
* added luma plugin ([#195](https://github.com/AleksandLexy/webcmd/issues/195)) ([79ea04a](https://github.com/AleksandLexy/webcmd/commit/79ea04a74228fc1aa17124cf519fb6fda1d73612))
* arbitrate persistent writes in Cloak daemon ([6d13e18](https://github.com/AleksandLexy/webcmd/commit/6d13e184f0f5fbd1b47ee766c10b5ee07fc3f7dc))
* attribute registered commands to plugin, override, or local origin ([fd07b85](https://github.com/AleksandLexy/webcmd/commit/fd07b850121ca17efdde5a2d53e923ca0dc8eed0))
* bootstrap Webcmd CLI from Codex skill ([83a1849](https://github.com/AleksandLexy/webcmd/commit/83a1849d0cce206e1ebac53a49cf0cad37f91a85))
* bridge core CLI commands to hosted mode ([#458](https://github.com/AleksandLexy/webcmd/issues/458)) ([1030b92](https://github.com/AleksandLexy/webcmd/commit/1030b92b1ae798466eb5b39092711e74f5baa313))
* browser run playwright sandbox ([54936c1](https://github.com/AleksandLexy/webcmd/commit/54936c14b05674432b08eb40976d8c503dec3e9c))
* **browser:** import Chrome cookies during local setup ([#485](https://github.com/AleksandLexy/webcmd/issues/485)) ([38ea705](https://github.com/AleksandLexy/webcmd/commit/38ea7054102905029e619795320651c43bb2b402))
* **browser:** restore runtime rollout with SLAB reuse ([#479](https://github.com/AleksandLexy/webcmd/issues/479)) ([29d4a21](https://github.com/AleksandLexy/webcmd/commit/29d4a21776de246636262067e5438bec33484a26))
* **browser:** support custom Chromium binaries with isolated profiles ([#462](https://github.com/AleksandLexy/webcmd/issues/462)) ([4efe7cc](https://github.com/AleksandLexy/webcmd/commit/4efe7cc84fdd59b16d8e30c0511616fba5bbf79c))
* **chatgpt:** add GPT-5.6 Pro model target ([bd31147](https://github.com/AleksandLexy/webcmd/commit/bd31147ebd6cbd3786d5536bf6e338d1c4e4f3cb))
* **chrome:** export webcmd Chrome profiles to native Chrome ([#500](https://github.com/AleksandLexy/webcmd/issues/500)) ([999c1a0](https://github.com/AleksandLexy/webcmd/commit/999c1a014113477900d9fd6130514c293a26281b))
* **cli:** add --format to profile list and report disconnected profiles ([#341](https://github.com/AleksandLexy/webcmd/issues/341)) ([c4832b1](https://github.com/AleksandLexy/webcmd/commit/c4832b124b353f21be3df080e953f24377610c1b))
* **cli:** add -f/--format to browser verify ([f1ec44d](https://github.com/AleksandLexy/webcmd/commit/f1ec44d978fb2610e03da91c9af5ed1a32bc6229))
* **cli:** add -f/--format to browser verify ([#351](https://github.com/AleksandLexy/webcmd/issues/351)) ([78a1d88](https://github.com/AleksandLexy/webcmd/commit/78a1d88eb7ecb184ffa9b0bebf41763ec81ce753))
* default browser windows to background ([e9e915c](https://github.com/AleksandLexy/webcmd/commit/e9e915c05dd734d4d3d64f999f1eef6b055b7ce3))
* default browser windows to background ([8e4ac7c](https://github.com/AleksandLexy/webcmd/commit/8e4ac7c25c3b04de161c595c3722926792d23163))
* drop hosted mode from webcmd setup ([#493](https://github.com/AleksandLexy/webcmd/issues/493)) ([5e5a258](https://github.com/AleksandLexy/webcmd/commit/5e5a258e569b6bb6b3a744ba995d0649822dd7e6))
* enhance screenshot functionality to restore viewport size and support CDP overrides ([d26ac62](https://github.com/AleksandLexy/webcmd/commit/d26ac62aac3af38670dc13a85d934bfc675b6b1b))
* enhance screenshot functionality to restore viewport size and support CDP overrides ([86a54ed](https://github.com/AleksandLexy/webcmd/commit/86a54edc59738b7cfad42207e06b6e60f66bd3b8))
* export AX snapshot helpers ([3b84852](https://github.com/AleksandLexy/webcmd/commit/3b8485264890e6c131eecb68b78823bbd2c240fd))
* export the verify fixture evaluator for hosted consumers ([bf9f331](https://github.com/AleksandLexy/webcmd/commit/bf9f331da085587b8a280282f4e13a833334d616))
* expose local web fetch and smart search skill ([9485e90](https://github.com/AleksandLexy/webcmd/commit/9485e90966211b0d3a7781cc83120beb2e86a6a9))
* **fetch:** add --raw to web fetch for selector discovery ([#419](https://github.com/AleksandLexy/webcmd/issues/419)) ([015d3ef](https://github.com/AleksandLexy/webcmd/commit/015d3ef583bb403d7dd1e9528fa5dfe3a8623aee))
* filter command list by tag ([9e7eedd](https://github.com/AleksandLexy/webcmd/commit/9e7eedd516542fbc52dbfedf66d9be2cf94d3b2a))
* **google:** add images search adapter ([151d523](https://github.com/AleksandLexy/webcmd/commit/151d52324fc9e9799a81aaba01b64b70a5933ce1))
* hold session lease for logical adapter runs ([0600ebf](https://github.com/AleksandLexy/webcmd/commit/0600ebff66e9569b4857791a4e4b924c9ff4d060))
* **hosted:** add authenticated artifact download command ([#438](https://github.com/AleksandLexy/webcmd/issues/438)) ([509ed35](https://github.com/AleksandLexy/webcmd/commit/509ed35c34d171370dd9acb3d9cd8a1594758366))
* **hosted:** add programmatic runner and MCP skill distribution ([#434](https://github.com/AleksandLexy/webcmd/issues/434)) ([1449f34](https://github.com/AleksandLexy/webcmd/commit/1449f340f50aa26cdc0c5a5948f3981b386fcfc7))
* **hosted:** remove profile create/get and --user-id, keep list/delete ([4a20fa6](https://github.com/AleksandLexy/webcmd/commit/4a20fa632836b1b365a953da8d449cac481ccb24))
* **hosted:** send sessionless browser init/verify to authoring route ([#439](https://github.com/AleksandLexy/webcmd/issues/439)) ([c071e0d](https://github.com/AleksandLexy/webcmd/commit/c071e0d48090a3ec7f86b157ecadba455dc6307a))
* **hosted:** workspace env/flag transport via X-Webcmd-Workspace ([8ba8080](https://github.com/AleksandLexy/webcmd/commit/8ba8080904d4142a257ad9884324b82666441b4a))
* **hosted:** workspace-scoped profiles CLI transport ([da8857c](https://github.com/AleksandLexy/webcmd/commit/da8857ce69a92dd1f3d34362ce1d457d43696f7d))
* implement site memory invariants for local mode ([e603e73](https://github.com/AleksandLexy/webcmd/commit/e603e73f793f0e5c3a3e72bb8cd01e416d062fd2))
* manage hosted profiles from cli ([5e4e6d3](https://github.com/AleksandLexy/webcmd/commit/5e4e6d3faace07b1b0e8d29fc699b0beaa598a96))
* migrate release tooling to openai ([#256](https://github.com/AleksandLexy/webcmd/issues/256)) ([3bad833](https://github.com/AleksandLexy/webcmd/commit/3bad833e6cb1508c2407ca4b7b60089d6ee8d29a))
* **npm:** add versions command ([1bde3bb](https://github.com/AleksandLexy/webcmd/commit/1bde3bb2a83b6feb25e0c679361dba137bcb4f92))
* package Webcmd as a Codex plugin ([9a1a642](https://github.com/AleksandLexy/webcmd/commit/9a1a6422a16de08bec596dcc8f855455ad17feea))
* persist per-SLAB-profile agent behavior and route humanizer input ([#499](https://github.com/AleksandLexy/webcmd/issues/499)) ([bb030f3](https://github.com/AleksandLexy/webcmd/commit/bb030f30fbea4582c76428e48f6499f6fa3363ff))
* **plugin:** add TechCrunch latest news ([#157](https://github.com/AleksandLexy/webcmd/issues/157)) ([7aa7388](https://github.com/AleksandLexy/webcmd/commit/7aa7388dd236fa964fc2392a58a0e58783f21eeb))
* **plugin:** add Y Combinator startup directory ([#155](https://github.com/AleksandLexy/webcmd/issues/155)) ([f0c061e](https://github.com/AleksandLexy/webcmd/commit/f0c061e599bf76260fe2abbbe14b9e00374dabb6))
* remove bundled skill links ([5403e3b](https://github.com/AleksandLexy/webcmd/commit/5403e3b6ba8331302ef82e6913d397bb33c4b85f))
* report overrides needing reconciliation after a plugin update ([ebd93b8](https://github.com/AleksandLexy/webcmd/commit/ebd93b8526f1f8300ad78fbca1e1f6206d59f21d))
* return local login handoffs immediately ([7399991](https://github.com/AleksandLexy/webcmd/commit/7399991db3c58d87bab8fac13df63ef15c892d47))
* **site-memory:** add local self-learning browser memory ([#475](https://github.com/AleksandLexy/webcmd/issues/475)) ([8df0b5e](https://github.com/AleksandLexy/webcmd/commit/8df0b5ecbfd12f95e08306bae5bd4920d5d65f59))
* **skills:** carry the learning loop in the browser skill ([38f3def](https://github.com/AleksandLexy/webcmd/commit/38f3def38562fa954046ff752fcb197fd0e001ce))
* support hosted plugin search and install ([09f941d](https://github.com/AleksandLexy/webcmd/commit/09f941de6885533fc33d19d9c5ea3b5af1f2d644))
* surface Cloak runtime update notice in webcmd update ([8311830](https://github.com/AleksandLexy/webcmd/commit/8311830bd6a15518490810c102c62a0645b960e0))
* surface override state in plugin list, webcmd list, and adapter status ([97515a1](https://github.com/AleksandLexy/webcmd/commit/97515a18e8c2afdfb56e7817b735ab9d4f7de737))
* tag search commands ([93c191d](https://github.com/AleksandLexy/webcmd/commit/93c191d66f71cebd125475cfd4dd94ceb020a0b4))
* **trip:** add international adapter ([c977405](https://github.com/AleksandLexy/webcmd/commit/c977405336aaf3b09c22788a1613badd8e181198))
* update documentation theme with custom styling, typography, and site logo ([845f3fc](https://github.com/AleksandLexy/webcmd/commit/845f3fc6fb3d96b96e84f2b4ae534a7f8ad27b8b))
* update HOSTED_LOCAL_COMMANDS to derive from HOSTED_ROOT_HELP for consistency ([2fd11eb](https://github.com/AleksandLexy/webcmd/commit/2fd11eb8e9e6ad7d63cf92a25e819cba13aee2a2))
* **youtube:** added video frame capture command ([#297](https://github.com/AleksandLexy/webcmd/issues/297)) ([290ab67](https://github.com/AleksandLexy/webcmd/commit/290ab67c2297934d05c82ffb19bf585635d8fce9))


### Bug Fixes

* accept command search metadata in manifests ([0690fe6](https://github.com/AleksandLexy/webcmd/commit/0690fe6a6e01449cec685de46e5323030099f882))
* accept hosted freshPage metadata ([8170e3c](https://github.com/AleksandLexy/webcmd/commit/8170e3ce77c517b995a5021b2610ec044fbb7a06))
* **adapters,output:** repair site drift and markdown/console output bugs ([355d75b](https://github.com/AleksandLexy/webcmd/commit/355d75b1d184a4b67a217f2f486383c1f70a3cb7))
* add structured adapter status reporting ([e230e4e](https://github.com/AleksandLexy/webcmd/commit/e230e4e6134a3e77ed7ce3a998b40328dcaca925))
* agent-browser and playwright cli support added for benchmarks ([#430](https://github.com/AleksandLexy/webcmd/issues/430)) ([cb9303f](https://github.com/AleksandLexy/webcmd/commit/cb9303f51d3c2191f883585981457d0f8334753b))
* align Codex plugin publisher metadata ([618bbcd](https://github.com/AleksandLexy/webcmd/commit/618bbcdf235b33016c0903af47c0d270e32aff54))
* allow docs sync review to comment on pull requests ([4b6a429](https://github.com/AleksandLexy/webcmd/commit/4b6a429519f912a81dc3b44564b6e189c7252740))
* allow overriding the verify row-shape top-level key cap ([#230](https://github.com/AleksandLexy/webcmd/issues/230)) ([cf4f015](https://github.com/AleksandLexy/webcmd/commit/cf4f015e6d357f00832c4b4ed0682a3d240b2b00)), closes [#218](https://github.com/AleksandLexy/webcmd/issues/218)
* allow publishing an existing release tag ([ddf23d7](https://github.com/AleksandLexy/webcmd/commit/ddf23d793634bbbc20fc7471de3b60bb8ed57372))
* benchmark setup and report updated  ([#395](https://github.com/AleksandLexy/webcmd/issues/395)) ([0e653e8](https://github.com/AleksandLexy/webcmd/commit/0e653e82797997d98f0a8117f8e10f2243086404))
* bound AX tree traversal ([e3088c9](https://github.com/AleksandLexy/webcmd/commit/e3088c9cd5a2046ec69fe0e206df9e2ddfeec4b8))
* **browser:** add btoa/atob/TextEncoder/TextDecoder to the run sandbox ([#344](https://github.com/AleksandLexy/webcmd/issues/344)) ([3169475](https://github.com/AleksandLexy/webcmd/commit/3169475faa44e8c5d494498bf918661db45e276d))
* **browser:** decode response bodies as UTF-8 text in the run sandbox ([#357](https://github.com/AleksandLexy/webcmd/issues/357)) ([ff1fa9f](https://github.com/AleksandLexy/webcmd/commit/ff1fa9fc2e8ed3a70bf86a02e0c714138ec3aab2))
* **browser:** default every daemon command to a background window ([#328](https://github.com/AleksandLexy/webcmd/issues/328)) ([53e0c34](https://github.com/AleksandLexy/webcmd/commit/53e0c3496ccc74203cb752223e19649ca067aabf))
* **browser:** don't reuse a dead page/context lease in browser run ([#324](https://github.com/AleksandLexy/webcmd/issues/324)) ([1e18076](https://github.com/AleksandLexy/webcmd/commit/1e1807672ced37dc2668971c603129673a97ab61))
* **browser:** improve run agent ergonomics ([#409](https://github.com/AleksandLexy/webcmd/issues/409)) ([cf4005c](https://github.com/AleksandLexy/webcmd/commit/cf4005cf0f289ddc7231b9dd2bfd38caef7394fe))
* **browser:** isolate persistent session pages ([#312](https://github.com/AleksandLexy/webcmd/issues/312)) ([85a2e5e](https://github.com/AleksandLexy/webcmd/commit/85a2e5ef9b993f6b6c009f3371b1ad4cddfe8dbf))
* **browser:** keep background Chromium profile alive ([#308](https://github.com/AleksandLexy/webcmd/issues/308)) ([a60b9ec](https://github.com/AleksandLexy/webcmd/commit/a60b9ec1f6be1a580f27fd061190b8f82cb191da))
* **browser:** keep installed Chrome profile loaded on macOS ([#487](https://github.com/AleksandLexy/webcmd/issues/487)) ([5dcc3b8](https://github.com/AleksandLexy/webcmd/commit/5dcc3b8be73209a1d6a0993aa679ef8896c2a030))
* **browser:** name the Cloak setContent hang instead of advising a longer timeout ([#448](https://github.com/AleksandLexy/webcmd/issues/448)) ([#528](https://github.com/AleksandLexy/webcmd/issues/528)) ([cd07f25](https://github.com/AleksandLexy/webcmd/commit/cd07f253f3b2ec2a51561bc51da5772ebf2f7ff0))
* **browser:** name the CloakBrowser session cap instead of "target closed" ([#225](https://github.com/AleksandLexy/webcmd/issues/225)) ([#467](https://github.com/AleksandLexy/webcmd/issues/467)) ([9255e2e](https://github.com/AleksandLexy/webcmd/commit/9255e2e5b0c4089775cb0f5bd7b14068ed15b596))
* **browser:** name the supported alternative in unsupported-API errors ([#343](https://github.com/AleksandLexy/webcmd/issues/343)) ([e37e36e](https://github.com/AleksandLexy/webcmd/commit/e37e36ea46b7ac7a484c1c4cb69d699953a66576))
* **browser:** repair doctor session and first cloak window ([#298](https://github.com/AleksandLexy/webcmd/issues/298)) ([7b49907](https://github.com/AleksandLexy/webcmd/commit/7b499075167460bd465e707cc4d4c36edb54ec56))
* **browser:** report the caller's line and column for browser-run compile errors ([#356](https://github.com/AleksandLexy/webcmd/issues/356)) ([5114777](https://github.com/AleksandLexy/webcmd/commit/5114777d66bd78e4e628336a5d25044b06e110cb))
* **browser:** serialize undefined run results as null ([#278](https://github.com/AleksandLexy/webcmd/issues/278)) ([5baa154](https://github.com/AleksandLexy/webcmd/commit/5baa154c37638a1a87ab0fe91c00c7dc6bdf6fa7))
* **browser:** tolerate pages closing during session cleanup ([#329](https://github.com/AleksandLexy/webcmd/issues/329)) ([4cee5c2](https://github.com/AleksandLexy/webcmd/commit/4cee5c2d64d7efd79555957d453db2a7af21ecc7))
* **browser:** use monotonic capture timeout ([#488](https://github.com/AleksandLexy/webcmd/issues/488)) ([0fe6207](https://github.com/AleksandLexy/webcmd/commit/0fe62078906e86cd8c524bfaa13de8d69d405a2d))
* bump js-yaml to 4.3.2 for GHSA-2883-xcg3-v3hh ([86bd7d2](https://github.com/AleksandLexy/webcmd/commit/86bd7d25bb4bf58c80c837c7e861ce0953de95ac))
* bump LinkedIn plugin runtime floor for 0.6.0 ([dbc23e1](https://github.com/AleksandLexy/webcmd/commit/dbc23e1df1ca5b7c6a10ed5f901f2c6bb2e738d5))
* **chrome:** debounce sync-to-chrome export and set the exported profile's display name ([#504](https://github.com/AleksandLexy/webcmd/issues/504)) ([a5bf11f](https://github.com/AleksandLexy/webcmd/commit/a5bf11fc77622667f9bb27c5e0f75b4d9139c34b))
* classify Product Hunt verification pages ([66833bf](https://github.com/AleksandLexy/webcmd/commit/66833bfce01eb73110b183c33b9dae697de47f14))
* clear override provenance and merge base on adapter reset ([04d8bef](https://github.com/AleksandLexy/webcmd/commit/04d8beffccfa5278b322db05f316c04c70cd30e9))
* **cli:** accept -f/--format and --json on every command ([#425](https://github.com/AleksandLexy/webcmd/issues/425)) ([a7cb86e](https://github.com/AleksandLexy/webcmd/commit/a7cb86e65888e8a1a378e52c4f5e9a371e576aba))
* **cli:** add recovery hints for common misguesses ([#410](https://github.com/AleksandLexy/webcmd/issues/410)) ([11ea187](https://github.com/AleksandLexy/webcmd/commit/11ea187b2f8ae36b3dd0f6bbc9632ef9a38b0c04))
* **cli:** clarify adapter authoring help ([#408](https://github.com/AleksandLexy/webcmd/issues/408)) ([524aeab](https://github.com/AleksandLexy/webcmd/commit/524aeabf783b40f8f0bdc75121db1312e6278793))
* **cli:** close eval gaps for formats, profiles, and plugins ([38fb1e4](https://github.com/AleksandLexy/webcmd/commit/38fb1e4c81c01d531246a11d3386401b90b6a908))
* **cli:** discover adapters authored with registerCommand ([#423](https://github.com/AleksandLexy/webcmd/issues/423)) ([b5bc04e](https://github.com/AleksandLexy/webcmd/commit/b5bc04ed53d29e98a2cbf04fad33102ffb8cce82))
* **cli:** do not report a cross-Profile session close as already closed ([#431](https://github.com/AleksandLexy/webcmd/issues/431)) ([03534c0](https://github.com/AleksandLexy/webcmd/commit/03534c01e82d7439cef48c5615129345b79a70b4))
* **cli:** download wait timeout must not tell agents to invent file contents ([#398](https://github.com/AleksandLexy/webcmd/issues/398)) ([ee08499](https://github.com/AleksandLexy/webcmd/commit/ee084992b885fb5c98721f79661a32154aae3e4b))
* **cli:** fail validate on unknown target instead of PASS ([#366](https://github.com/AleksandLexy/webcmd/issues/366)) ([38a5a0e](https://github.com/AleksandLexy/webcmd/commit/38a5a0e747c1a880e8c401fc2342b8e506668ffb))
* **cli:** give every site command a description and structured help ([#422](https://github.com/AleksandLexy/webcmd/issues/422)) ([f28cefa](https://github.com/AleksandLexy/webcmd/commit/f28cefa5c34c812abf989d8f1fd7fb008ca506ac))
* **cli:** honour -f json on the error envelope ([#368](https://github.com/AleksandLexy/webcmd/issues/368)) ([07886d8](https://github.com/AleksandLexy/webcmd/commit/07886d80852c3b4246bc34ddc65ed74f93498631))
* **cli:** label plugin search as catalog discovery, not web search ([#396](https://github.com/AleksandLexy/webcmd/issues/396)) ([6299aa8](https://github.com/AleksandLexy/webcmd/commit/6299aa8a82abfc0ad15122d4fd719d0f50159fe1))
* **cli:** make session close accept --session and be idempotent ([#420](https://github.com/AleksandLexy/webcmd/issues/420)) ([06821f4](https://github.com/AleksandLexy/webcmd/commit/06821f4651ab4b87929796a302528c3da8291a91))
* **cli:** name the owning Profile when a Session lookup misses ([#406](https://github.com/AleksandLexy/webcmd/issues/406)) ([6da2859](https://github.com/AleksandLexy/webcmd/commit/6da2859739af1b13bf029e6655cd3c0845bedbc7))
* **cli:** name the removed setup flags instead of a generic unknown-flag error ([#509](https://github.com/AleksandLexy/webcmd/issues/509)) ([93052ec](https://github.com/AleksandLexy/webcmd/commit/93052ecface33e69de8dbd303fd24b6c826f50d5))
* **cli:** never prompt in webcmd setup when stdin is not a TTY ([#369](https://github.com/AleksandLexy/webcmd/issues/369)) ([59257d4](https://github.com/AleksandLexy/webcmd/commit/59257d43715e253200be1ed6fc093f3d15c654a2))
* **cli:** one error envelope and exit 2 for every usage error ([#424](https://github.com/AleksandLexy/webcmd/issues/424)) ([527e623](https://github.com/AleksandLexy/webcmd/commit/527e6231fdb3a3617fb4be3a78b7a971b3e8bd08))
* **cli:** point EMPTY_RESULT at adapter repair, not login ([#401](https://github.com/AleksandLexy/webcmd/issues/401)) ([0061b0b](https://github.com/AleksandLexy/webcmd/commit/0061b0be466df39b838e2ad5bca33fb6b172004d))
* **cli:** popup wait timeout must not tell agents to page.goto the opener ([#397](https://github.com/AleksandLexy/webcmd/issues/397)) ([f640a3e](https://github.com/AleksandLexy/webcmd/commit/f640a3e6e1677ec16e9e826c4d1969c5e2aa5f7c))
* **cli:** reject unknown profile use instead of poisoning the default ([#367](https://github.com/AleksandLexy/webcmd/issues/367)) ([49cc701](https://github.com/AleksandLexy/webcmd/commit/49cc701c606852962ade5a6b452a231e37b84cd4))
* **cli:** remove browser fork, add adapter override to hosted mode ([#361](https://github.com/AleksandLexy/webcmd/issues/361)) ([3c2ab10](https://github.com/AleksandLexy/webcmd/commit/3c2ab10ccbee5baae3d12fe3530a1347cfa0a6c8))
* **cli:** report built-in command errors instead of crashing ([#363](https://github.com/AleksandLexy/webcmd/issues/363)) ([7afaf7c](https://github.com/AleksandLexy/webcmd/commit/7afaf7c2bd64b1e62675d1ae29f0f30ce76d7a44))
* **cli:** resolve installSource from the catalog and name the data: popup block ([#429](https://github.com/AleksandLexy/webcmd/issues/429)) ([e179e25](https://github.com/AleksandLexy/webcmd/commit/e179e25654744ec2846e7d17fb14822417334ea5))
* **cli:** route unknown subcommands through the shared error envelope ([#427](https://github.com/AleksandLexy/webcmd/issues/427)) ([8b765c1](https://github.com/AleksandLexy/webcmd/commit/8b765c1ff905eaa79ae734a18f9d48e31a6ae1f7))
* **cli:** suggest the real command instead of a plugin that does not exist ([#421](https://github.com/AleksandLexy/webcmd/issues/421)) ([9df84e3](https://github.com/AleksandLexy/webcmd/commit/9df84e3b5ca939ea6a05ca3bcba53e75b4a35b79))
* **cli:** unknown flags exit 2 and list valid flags ([#370](https://github.com/AleksandLexy/webcmd/issues/370)) ([7848080](https://github.com/AleksandLexy/webcmd/commit/78480808161df8df36f56b5695ad8c534cd82dbf))
* **cli:** update help text formatting and structure ([#486](https://github.com/AleksandLexy/webcmd/issues/486)) ([a28119b](https://github.com/AleksandLexy/webcmd/commit/a28119bd25001f4ee3d34b7dea890afe2dd53190))
* close plugin override review gaps ([17b5e50](https://github.com/AleksandLexy/webcmd/commit/17b5e5020f91bbc30b0a01a6401025b89354bd27))
* coalesce concurrent page leases ([6c48e3d](https://github.com/AleksandLexy/webcmd/commit/6c48e3dcbf43b2ee59058eb46fa58543b6a70bea))
* condition autofix auth handoff ([68a4e8c](https://github.com/AleksandLexy/webcmd/commit/68a4e8c608917860bdcf016fd9057b05c531df92))
* copy sibling plugin files when creating an adapter override ([#533](https://github.com/AleksandLexy/webcmd/issues/533)) ([bd6096e](https://github.com/AleksandLexy/webcmd/commit/bd6096e29d8cf4d3030eb55a0bcce5cad015c956))
* correct layer numbering in README for clarity ([#205](https://github.com/AleksandLexy/webcmd/issues/205)) ([9ff79ed](https://github.com/AleksandLexy/webcmd/commit/9ff79ed7bbd79f0c46bdf4996d33c2a35075dbf6))
* detect overrides against installed plugins instead of the removed bundled clis ([c7df07c](https://github.com/AleksandLexy/webcmd/commit/c7df07ce63fab987f3993f229fe64015a667adeb))
* **docs-review:** constrain the advisory review with the schema it already defines ([#466](https://github.com/AleksandLexy/webcmd/issues/466)) ([625254d](https://github.com/AleksandLexy/webcmd/commit/625254d1343cc66adb2f8cdf6dd1ffa30dfb0e73))
* **docs:** show navigation logo ([f8e4542](https://github.com/AleksandLexy/webcmd/commit/f8e4542350c6c385d710feefb4732a45ace4f94a))
* **docs:** show navigation logo ([37042f7](https://github.com/AleksandLexy/webcmd/commit/37042f71b2a7bbbf4e3d673dd88a425c7e540a40))
* **doctor:** honor background window mode ([a42547c](https://github.com/AleksandLexy/webcmd/commit/a42547c980580540409412cad167a19f6c4954bf))
* **doctor:** honor background window mode ([b8224d0](https://github.com/AleksandLexy/webcmd/commit/b8224d0da9d0923d1807bb158d33f9b7ccb3b95d))
* **doctor:** install browser before live timeout ([#237](https://github.com/AleksandLexy/webcmd/issues/237)) ([80624bb](https://github.com/AleksandLexy/webcmd/commit/80624bb6515d3b1129e2947b7583ba00a98860d2))
* don't let doctor crash when adapter override detection fails ([2b9a5c4](https://github.com/AleksandLexy/webcmd/commit/2b9a5c4084f393c7c57d20ee8734245ef0d07ba6))
* **download:** isolate temp files and reject duplicate download targets ([#333](https://github.com/AleksandLexy/webcmd/issues/333)) ([90a37f0](https://github.com/AleksandLexy/webcmd/commit/90a37f00bbd759979470c5e0cc83b2b806b4855d))
* extend docs sync review model timeout ([673dfa1](https://github.com/AleksandLexy/webcmd/commit/673dfa199b8c354100d80aeb47c8efb569a1096b))
* forward waitUntil through navigate so adapters can skip the load-event wait ([edd9808](https://github.com/AleksandLexy/webcmd/commit/edd9808f638378f6680c82c4ddc28a007cdb5eb5))
* forward waitUntil through navigate so adapters can skip the load-event wait ([741e21e](https://github.com/AleksandLexy/webcmd/commit/741e21e04c15aa78da43af813fa29a7970cd0a72)), closes [#106](https://github.com/AleksandLexy/webcmd/issues/106)
* harden docs review structured output ([#259](https://github.com/AleksandLexy/webcmd/issues/259)) ([0b03172](https://github.com/AleksandLexy/webcmd/commit/0b03172292368ce447ec42d737b9267839168247))
* harden local auth handoff ([b6545a2](https://github.com/AleksandLexy/webcmd/commit/b6545a2f1cae48660c469bbaebcc7ea5ddab1e31))
* harden local site memory filesystem reads ([efbd2e7](https://github.com/AleksandLexy/webcmd/commit/efbd2e7fd0f79d39abc14458bc7151eab52bd0f7))
* honor waitUntil none in direct CDP navigation ([52b03c6](https://github.com/AleksandLexy/webcmd/commit/52b03c6067b8262b2a84f1d46135de21e4b2d369))
* honour the web fetch timeout budget end to end ([#249](https://github.com/AleksandLexy/webcmd/issues/249)) ([#265](https://github.com/AleksandLexy/webcmd/issues/265)) ([263c446](https://github.com/AleksandLexy/webcmd/commit/263c446833d3f44d6bd282c989ef91bbb8c94232))
* **hosted:** accept expiresAt in browser run responses ([37159eb](https://github.com/AleksandLexy/webcmd/commit/37159eb9169bf68e9152b9a2bac969c310de7f96))
* **hosted:** accept expiresAt in browser run responses ([90e57f9](https://github.com/AleksandLexy/webcmd/commit/90e57f9a39ac3883d4e5a40204b57207f1c43f9c))
* **hosted:** accept object error.details from Cloud ([#440](https://github.com/AleksandLexy/webcmd/issues/440)) ([de6570a](https://github.com/AleksandLexy/webcmd/commit/de6570a7f62982d3fa02546bdeb0d7cfe4ddf5f5))
* **hosted:** resolve --workspace= form and drop dead profile client code ([ae0b8ad](https://github.com/AleksandLexy/webcmd/commit/ae0b8ad35233a73a7ad42844a27bdcd49c724809))
* **hosted:** stop duplicating usage errors and align the subcommand list ([#428](https://github.com/AleksandLexy/webcmd/issues/428)) ([7bb7ba3](https://github.com/AleksandLexy/webcmd/commit/7bb7ba3310b24f8350fc181fcfa11f869ba4ae58))
* **instagram:** fetch user feed by username ([6dc6df8](https://github.com/AleksandLexy/webcmd/commit/6dc6df8ec597fc6761dd0146d66ddac3f79b56fe))
* isolate logical adapter run contexts ([3ee5249](https://github.com/AleksandLexy/webcmd/commit/3ee5249756ed440bb68ccd7ca9f3750a932f53ec))
* keep auth handoff skills mode neutral ([21da95c](https://github.com/AleksandLexy/webcmd/commit/21da95ca9e26d0e34a274ffbe75612d15c826bcd))
* keep background tabs from stealing focus ([4217087](https://github.com/AleksandLexy/webcmd/commit/42170875419bc76e7bf7635269fe71b7badd9f3e))
* keep background tabs from stealing focus ([edf3487](https://github.com/AleksandLexy/webcmd/commit/edf3487b5b1f76acdecbf9139e900a89941277f0))
* keep cloak wrapper on latest free chromium line ([2c6845e](https://github.com/AleksandLexy/webcmd/commit/2c6845e49249562446a4fde6b27cf93abbd1658c))
* keep hosted commands on cloud ([83c06c1](https://github.com/AleksandLexy/webcmd/commit/83c06c148374833cc7509b10f932bd5271badd38))
* keep hosted tests compatible with release version ([ebf62e0](https://github.com/AleksandLexy/webcmd/commit/ebf62e07d7147321181c077a34f26e5c21685fe2))
* keep override tests portable on windows ([73eb24d](https://github.com/AleksandLexy/webcmd/commit/73eb24df1c6bdde2c684e67db4c8363576cd9b6b))
* keep pack JSON stdout clean ([2c11490](https://github.com/AleksandLexy/webcmd/commit/2c1149065c70730af0620b0369979cc8fd384984))
* keep site-blocked errors edge-safe ([958f076](https://github.com/AleksandLexy/webcmd/commit/958f076c84ebb469e25e8cfa04c3d347773a7cdc))
* let ~/.webcmd/clis override installed plugins ([2c79330](https://github.com/AleksandLexy/webcmd/commit/2c79330ad44ed67656230d3c62ceb411525357d3))
* **linkedin:** bump webcmd peer-dependency floor to &gt;=0.7.4 ([#371](https://github.com/AleksandLexy/webcmd/issues/371)) ([a7dec7b](https://github.com/AleksandLexy/webcmd/commit/a7dec7b383400747fe164494f5dc48ea9914ffb0))
* load plugin from marketplace snapshot ([5989816](https://github.com/AleksandLexy/webcmd/commit/5989816814cc54a040c29301c3f751179dbb8577))
* **local-cloak:** honour waitUntil when opening a tab with a url ([9bfce95](https://github.com/AleksandLexy/webcmd/commit/9bfce95bf4a013aa7bd725f0a78aa0009b8042fc)), closes [#210](https://github.com/AleksandLexy/webcmd/issues/210)
* **local-cloak:** honour waitUntil when opening a tab with a url ([#316](https://github.com/AleksandLexy/webcmd/issues/316)) ([4b114ba](https://github.com/AleksandLexy/webcmd/commit/4b114ba3beb3a80d955bf8359d34f5d7f04f66f5))
* **logger:** reuse normalized verbose gating ([9c4795c](https://github.com/AleksandLexy/webcmd/commit/9c4795c03da11c6651a55d0b86a0bf89e4451dda))
* make -v effective in hosted, browser, and auth commands ([6b62675](https://github.com/AleksandLexy/webcmd/commit/6b626752cd44c85df2cb30d69d7efe13ee54c43d)), closes [#174](https://github.com/AleksandLexy/webcmd/issues/174)
* make -v effective in hosted, browser, and auth commands ([#315](https://github.com/AleksandLexy/webcmd/issues/315)) ([9c70a62](https://github.com/AleksandLexy/webcmd/commit/9c70a628fb58243bb30ddb9e9e91b099f17b6c78))
* make session release best effort ([8e43fb7](https://github.com/AleksandLexy/webcmd/commit/8e43fb774872732dc74187cf96089d3020cdccae))
* make webcmd discovery truncation-safe ([5688302](https://github.com/AleksandLexy/webcmd/commit/568830280951fbac03ff61bf54d6a6dae9506b94))
* make Webcmd discovery truncation-safe ([1986089](https://github.com/AleksandLexy/webcmd/commit/198608904685d38d1d1a5cba95a7931594b65be7))
* narrow adapter status missing directory handling ([4b23042](https://github.com/AleksandLexy/webcmd/commit/4b230423853b8d9cb86a1888704b760cef0f0ba6))
* normalize Hacker News job URLs ([e19b7cb](https://github.com/AleksandLexy/webcmd/commit/e19b7cb3c057e78f4dbf32bc6db6a93fe8b70007))
* **observation:** redact Basic/Negotiate/NTLM auth credentials in raw text, not just Bearer ([#426](https://github.com/AleksandLexy/webcmd/issues/426)) ([fe42235](https://github.com/AleksandLexy/webcmd/commit/fe42235940725cc7c245073940caad5e74557e55))
* omit links for internal plugin authors ([#214](https://github.com/AleksandLexy/webcmd/issues/214)) ([06806b8](https://github.com/AleksandLexy/webcmd/commit/06806b86ee2c1434a591a684ae643c617cca91ed))
* parse fenced docs review json ([#260](https://github.com/AleksandLexy/webcmd/issues/260)) ([00df65a](https://github.com/AleksandLexy/webcmd/commit/00df65a74152360092d54a86c97f991d23a07acc))
* preserve cloud parity for blocked sites and fresh pages ([8fc667b](https://github.com/AleksandLexy/webcmd/commit/8fc667bc23760dc5f0d19fb6e530d29a4e46f762))
* preserve hosted routing for local-only commands ([1fbe69d](https://github.com/AleksandLexy/webcmd/commit/1fbe69d7ac24dc55d4e359b2d284635abf11be20))
* prevent adapter option collisions from bricking the CLI ([#529](https://github.com/AleksandLexy/webcmd/issues/529)) ([af4a573](https://github.com/AleksandLexy/webcmd/commit/af4a57349ed3e84af3c3feda453096abfa144709))
* prune stale stable-root skill symlinks on add/update ([#495](https://github.com/AleksandLexy/webcmd/issues/495)) ([bb253d3](https://github.com/AleksandLexy/webcmd/commit/bb253d3de3d590ccdc21e6b3f4b0e15c9240e4cf))
* recover Cloak sessions and arbitrate persistent writes ([b737172](https://github.com/AleksandLexy/webcmd/commit/b737172351d58aba70fccc94288319b50417d842))
* recover closed Cloak profile contexts ([70b3668](https://github.com/AleksandLexy/webcmd/commit/70b3668758542cc548c9a36c9cd25c78e617e5c7))
* reject symlinked site memory path segments ([67d8f85](https://github.com/AleksandLexy/webcmd/commit/67d8f85ac9d6923152e4f81208988b8719660b50))
* release safe late adapter outcomes ([646ff8e](https://github.com/AleksandLexy/webcmd/commit/646ff8e9ddd8ff8f1cd8a963e755abb82b41acb3))
* release standalone plugin compatibility as 0.7.11 ([#473](https://github.com/AleksandLexy/webcmd/issues/473)) ([9ab8e13](https://github.com/AleksandLexy/webcmd/commit/9ab8e1314bfce88ba99380f8b8bf911ef0acd772))
* **release:** restore dependency versions ([0db8dfb](https://github.com/AleksandLexy/webcmd/commit/0db8dfbc417ee05ec0703cabfc4378e659e3ed81))
* require auth handoff verification ([501a1f2](https://github.com/AleksandLexy/webcmd/commit/501a1f2dac6132ab712355d1c41a93933dc52761))
* require OpenAI-generated release notes ([#307](https://github.com/AleksandLexy/webcmd/issues/307)) ([9536edf](https://github.com/AleksandLexy/webcmd/commit/9536edf834d2df93d79f0f09dc55ac1842bdde6c))
* resolve cloak browser version in LocalCloakRuntimeProvider and CloakSessionManager ([#102](https://github.com/AleksandLexy/webcmd/issues/102)) ([a221f86](https://github.com/AleksandLexy/webcmd/commit/a221f86c3dd69db547b8de23dee234033c16b191))
* restrict Windows diagnostic artifacts ([4052403](https://github.com/AleksandLexy/webcmd/commit/4052403e3b06e88bb427f3fe97d7f594054e04dc))
* retain daemon liveness after response timeout ([c9b2f4e](https://github.com/AleksandLexy/webcmd/commit/c9b2f4e049b3ed254fe59ad146016ec919e1c29c))
* retry background Chromium launch via lsregister ([#302](https://github.com/AleksandLexy/webcmd/issues/302)) ([2581128](https://github.com/AleksandLexy/webcmd/commit/25811282d56b0150831ba095811b7e40ecd9149e))
* return empty adapter status as json ([410ee3a](https://github.com/AleksandLexy/webcmd/commit/410ee3af5650af332ef22f43ee0170a54c6956e7))
* run install lifecycle scripts on Windows ([#483](https://github.com/AleksandLexy/webcmd/issues/483)) ([3851922](https://github.com/AleksandLexy/webcmd/commit/38519220f697b3dcc61bc53572f9d0027c206892))
* run package bin checks through Windows shell ([afe7e23](https://github.com/AleksandLexy/webcmd/commit/afe7e23640000e163ca5cef8c1806b89d5962734))
* run src/browser unit tests in CI and stabilize the vendor digest ([#238](https://github.com/AleksandLexy/webcmd/issues/238)) ([b9a0432](https://github.com/AleksandLexy/webcmd/commit/b9a0432cee5774a5302286ddd0745a5e4d873a2c))
* run verify fixture export contract in unit tests ([9355ba3](https://github.com/AleksandLexy/webcmd/commit/9355ba39461b964da98372f9309991d48c40b5f7))
* scope commitHash lookup to homeDir in adapter override provenance ([9a9af53](https://github.com/AleksandLexy/webcmd/commit/9a9af53f5bd59c4a20045d7bdcfd66e400fd1a9c))
* scope override reconciliation to updated plugins ([002c8d7](https://github.com/AleksandLexy/webcmd/commit/002c8d7602380577aebaf27e6e1d977d772f35f5))
* scope skills remove to one provider/scope, like skills add ([#492](https://github.com/AleksandLexy/webcmd/issues/492)) ([5b8dfdb](https://github.com/AleksandLexy/webcmd/commit/5b8dfdbbb4a3b070d9d7f6dc3d40d03593a43db9))
* serialize background page creation ([eff1631](https://github.com/AleksandLexy/webcmd/commit/eff1631f0f0eb9f60440e3d36125a2ac8b2e1a15))
* settle popup and download event handles without deadlock ([#463](https://github.com/AleksandLexy/webcmd/issues/463)) ([b6be21b](https://github.com/AleksandLexy/webcmd/commit/b6be21b6fac0ab7aec41ee2c11c025a3f7b703f6))
* show disconnected profiles in plain output, offer sync-to-chrome interactively ([#502](https://github.com/AleksandLexy/webcmd/issues/502)) ([795e538](https://github.com/AleksandLexy/webcmd/commit/795e538f8357e5f8978b7d5b11dc6490838fc01d))
* **site-memory:** lock site memory writes across processes ([#321](https://github.com/AleksandLexy/webcmd/issues/321)) ([9d64d96](https://github.com/AleksandLexy/webcmd/commit/9d64d96cf1090396945e4be122bed77d9c26c310))
* **site-memory:** retry transient Windows lock opens ([#446](https://github.com/AleksandLexy/webcmd/issues/446)) ([ec661cc](https://github.com/AleksandLexy/webcmd/commit/ec661cc13652a7a982525e308fda842ebe8812af))
* **site-memory:** stop a stale file lock from being stolen while the owner is still alive ([#496](https://github.com/AleksandLexy/webcmd/issues/496)) ([e1ca0a5](https://github.com/AleksandLexy/webcmd/commit/e1ca0a5e5cb77e3566a6835ae161be52128e9ab9)), closes [#432](https://github.com/AleksandLexy/webcmd/issues/432)
* **skill:** add a site-named fast path to smart-search ([#248](https://github.com/AleksandLexy/webcmd/issues/248)) ([#269](https://github.com/AleksandLexy/webcmd/issues/269)) ([d23e273](https://github.com/AleksandLexy/webcmd/commit/d23e27377c3708cf3c9f873465a9d1006bf3969f))
* **skills:** correct candidate qualification and completion rules ([03f18e3](https://github.com/AleksandLexy/webcmd/commit/03f18e37e18ab9ac141685247d013092584eb234))
* **skills:** keep failed learning recoverable, not rolled back ([d40d867](https://github.com/AleksandLexy/webcmd/commit/d40d867812e2da07641837e209d2fecc01374dfb))
* **skills:** keep learning failures out of normal output ([86ab11a](https://github.com/AleksandLexy/webcmd/commit/86ab11a8f9c258d038abe7df280790a005c79c00))
* **skills:** keep recurrence capture behind the qualification bar ([f6a0418](https://github.com/AleksandLexy/webcmd/commit/f6a04188bf95207fe5ac408d182db9af0d8a594f))
* stop the plugin update guard firing on npm install artifacts ([#267](https://github.com/AleksandLexy/webcmd/issues/267)) ([a97129f](https://github.com/AleksandLexy/webcmd/commit/a97129f6c43a9b2606d4745fac980b724f917eb0))
* support multi-word plugin search ([#285](https://github.com/AleksandLexy/webcmd/issues/285)) ([74af318](https://github.com/AleksandLexy/webcmd/commit/74af318919fe543e885347e6d46a95627851f2d4))
* surface adapter status json errors ([8a26315](https://github.com/AleksandLexy/webcmd/commit/8a2631507e970a42f24ad018741cbc39a50d2a7b))
* surface workspace, origin, and browser-init in hosted help ([#464](https://github.com/AleksandLexy/webcmd/issues/464)) ([7ce0248](https://github.com/AleksandLexy/webcmd/commit/7ce0248fe549281cb3f9b37636773316a7c4c76f))
* sync hosted profile docs for completion ([a53c51d](https://github.com/AleksandLexy/webcmd/commit/a53c51da44d95815f4bd2bf7eaf8023a5ccc9e0f))
* tighten Cloak page recovery boundaries ([aaa6d99](https://github.com/AleksandLexy/webcmd/commit/aaa6d9955891ee3e98d03e5cd68fd3b0a7a3fd78))
* traverse ignored AX intermediaries ([01a91c5](https://github.com/AleksandLexy/webcmd/commit/01a91c5b607a20e6c68c4664ed2b10ee524298d2))
* typos ([a2f69a9](https://github.com/AleksandLexy/webcmd/commit/a2f69a90cd665f2daa0706dd320fc920d4a29cab))
* use a lighter review model ([#257](https://github.com/AleksandLexy/webcmd/issues/257)) ([fe58da9](https://github.com/AleksandLexy/webcmd/commit/fe58da96be77ea08c6707566c374587bd80c1e30))
* use Impit fetch clients ([e7524d0](https://github.com/AleksandLexy/webcmd/commit/e7524d0acdc9bb42a1766a059d07aaa1e0ca3a8e))
* validate each override record and assert sha256 stability in tests ([97dd2c8](https://github.com/AleksandLexy/webcmd/commit/97dd2c84ce36b43299c280fb36017259b9d035df))
* validate provenance before empty reset ([598c43f](https://github.com/AleksandLexy/webcmd/commit/598c43f4e8427ad70707f5bc9aad61cf8c3b9de3))
* validate session lease process ids ([26b2b74](https://github.com/AleksandLexy/webcmd/commit/26b2b74175459d028805b1ce186b1cc30c840ab1))


### Performance Improvements

* cache the resolved cloakbrowser version instead of re-reading it per status call ([#213](https://github.com/AleksandLexy/webcmd/issues/213)) ([b5189e3](https://github.com/AleksandLexy/webcmd/commit/b5189e33743ffa718c12b8e0dca5618719a36d6b))


### Miscellaneous Chores

* force release version to 0.8.2 ([8835e59](https://github.com/AleksandLexy/webcmd/commit/8835e59d4b1e11ca69aa744be68829a6c5b21f0b))
* release 0.7.4 ([2e2b3ab](https://github.com/AleksandLexy/webcmd/commit/2e2b3abfb7f31ef605965ab9bd6366693f7ea8f2))
* release webcmd 0.8.1 ([1489cf0](https://github.com/AleksandLexy/webcmd/commit/1489cf09dfe431d590611dd85d7cebbc12b3722b))

## [0.8.4](https://github.com/agentrhq/webcmd/compare/webcmd-v0.8.3...webcmd-v0.8.4) (2026-09-08)

### Improvements
- `webcmd setup` now offers interactive Chrome profile syncing when Chrome is selected. The new prompt defaults to disabled and does not appear when the option was already specified.

### Fixes
- `webcmd profile list` now shows saved but disconnected profiles in plain-text output, even when no runtime profiles are currently connected.
- Chrome profile exports now run shortly after command activity, even when tabs remain open. Rapid commands are debounced into a single export without closing browsers or pages.
- Exported Chrome profiles now use their webcmd alias as the display name when registration succeeds. This naming update is best-effort when Chrome is already running.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7)

## [0.8.3](https://github.com/agentrhq/webcmd/compare/webcmd-v0.8.2...webcmd-v0.8.3) (2026-09-08)

### Highlights
- Added `webcmd setup --browser chrome --sync-to-chrome` to automatically copy profile cookies into a webcmd-managed native Chrome profile when the browser runtime closes. The profile is registered with Chrome in the background and can then be opened directly in Chrome.
- Added persistent, versioned agent behavior settings for each native SLAB profile, providing consistent humanized browser interactions across daemon sessions.

### Improvements
- Humanized input now avoids intentional mistypes in sensitive fields such as passwords, payment fields, and one-time-code inputs.
- Disposing an agent page now cancels in-progress humanized input and delays immediately.
- Playwright tracing snapshots are disabled on agent-controlled pages.

### Fixes
- Browser network-capture waits now use monotonic elapsed time, preventing premature timeouts when the system clock changes.

### Contributors
[@AcidicSoil](https://github.com/AcidicSoil) | [@ankitranjan7](https://github.com/ankitranjan7) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.8.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.8.1...webcmd-v0.8.2) (2026-09-07)

### Improvements
- `webcmd setup` now exclusively configures local browser mode. The hosted/local prompt and the `--mode` and `--api-key` options have been removed. Browser selection, Chrome cookie import, status reporting, and daemon restart behavior remain available.
- On first access to a product without local site memory, Webcmd now requests a seed from `https://api.webcmd.dev` by default. The unauthenticated request sends only the resolved product/domain, uses a two-second timeout, and is not retried. Set `WEBCMD_GLOBAL_MEMORY=off` to disable lookups; `WEBCMD_GLOBAL_MEMORY_URL` remains available as a developer or test override.

### Fixes
- `webcmd skills remove` now removes skills from only one provider and scope—or one custom `--path`—instead of scanning every supported location. It supports `--provider` and `--scope`, prompts for them interactively when needed, and includes them in JSON output. Stable links under `~/.webcmd/skills` are no longer removed by this command.
- `webcmd skills add` and `webcmd skills update` now prune stale symlinks from `~/.webcmd/skills` while preserving user-owned entries that are not symlinks.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7)

## [0.8.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.8.0...webcmd-v0.8.1) (2026-09-04)

### Highlights
- Local Chrome setup can now import cookies from installed Chrome profiles, allowing Webcmd to start with existing sign-ins. Setup maps Chrome’s default profile to Webcmd’s `default` profile and creates stable names for additional profiles.
- Use `--chrome-profile` to import one Chrome profile, or `--import-chrome-cookies` and `--no-import-chrome-cookies` to control cookie import in non-interactive setup.

### Improvements
- Redesigned `webcmd --help` with an ASCII banner, clearer command groups, global options, examples, agent guidance, and dynamic site/external CLI lists. Structured JSON and YAML help remain unchanged.
- Browser readiness messages now identify the configured runtime and provide relevant guidance for SLAB, Cloak, Chrome, and custom runtimes.

### Fixes
- Improved SLAB session orchestration:
  - Native profile IDs such as `Profile 1` are now supported.
  - `session list` exposes unbound SLAB windows as temporary `discovered` sessions.
  - `browser tabs` discovers pages without focusing or claiming them.
  - `browser bind --page <page-id>` claims the page’s complete window, including sibling tabs.
  - Closing an adopted human session detaches Webcmd while leaving the window open.
  - `browser close --page <page-id>` can close an exact tab; `--force` permits closing adopted human tabs.
  - Explicit session closure now cleans up SLAB session records correctly.
  - The initial blank page is claimed instead of leaving an unowned tab behind.
- Fixed installed Chrome on macOS unloading its profile or terminating after the last visible probe window closes.
- Browser daemon startup no longer inherits caller-owned temporary-directory environment variables, improving reliability when launched from short-lived environments.

### Contributors
[@rajarshidattapy](https://github.com/rajarshidattapy) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.8.0](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.11...webcmd-v0.8.0) (2026-09-02)


### Features

* **browser:** restore runtime rollout with SLAB reuse ([#479](https://github.com/agentrhq/webcmd/issues/479)) ([ae87b4a](https://github.com/agentrhq/webcmd/commit/ae87b4a8aae700c57af8dc5f1a41684d6aa5b160))
* **browser:** support custom Chromium binaries with isolated profiles ([#462](https://github.com/agentrhq/webcmd/issues/462)) ([fde64e2](https://github.com/agentrhq/webcmd/commit/fde64e295575b02ccfaed15dfd78156d642c3806))
* **site-memory:** add local self-learning browser memory ([#475](https://github.com/agentrhq/webcmd/issues/475)) ([018b723](https://github.com/agentrhq/webcmd/commit/018b7239ceb413691034497c35a3016a4a2654b5))

## [0.7.11](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.10...webcmd-v0.7.11) (2026-08-31)

### Fixes
- Hosted help now includes `--workspace <id>`, `WEBCMD_WORKSPACE`, and the `session` and `site` command groups.
- Unknown site commands now suggest using `webcmd browser init <site>/<command>` to author the missing command.
- Hosted `webcmd list` output now reports command origins consistently as `builtin`, `plugin:<name>`, `local`, or `override:<plugin>`.
- Fixed browser runs hanging after popup or download events fired. `page.waitForEvent('popup')` and `page.waitForEvent('download')` now resolve correctly, while event-specific timeouts are honored when no event occurs.

### Adapters
- Moved 123 community adapters to the standalone [`agentrhq/webcmd-plugins`](https://github.com/agentrhq/webcmd-plugins) repository without behavioral changes.
- Preserved compatibility for existing official source identifiers by normalizing legacy `agentrhq/webcmd` sources to the new repository.
- The standalone community plugin catalog requires Webcmd 0.7.11 or newer.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7)

## [0.7.10](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.9...webcmd-v0.7.10) (2026-08-28)

### Highlights
- Hosted mode can now negotiate and run core commands advertised by Webcmd Cloud, including diagnostics, profile lifecycle, and plugin catalog commands. Help, completion, and execution only expose capabilities supported by the connected Cloud service.
- Registered external CLIs can now run locally while Webcmd is configured for hosted mode. Arguments and child exit codes are preserved, and hosted sites take precedence if names collide.

### Improvements
- Hosted help and shell completion now advertise locally handled `skills`, `update`, and `external` commands.
- Hosted root help now includes `session`, `site`, and `--workspace <id>`, including the `WEBCMD_WORKSPACE` environment-variable alternative.
- Hosted authentication commands now use the same grammar, flags, choices, and help as local mode.
- `webcmd profile use` now stores a validated hosted profile preference locally.
- Hosted command lists retain unavailable commands as `LOCAL` entries and report origins consistently as `builtin`, `plugin:<name>`, `local`, or `override:<plugin>`.
- Unknown site subcommands now suggest the corresponding authoring command, such as `webcmd browser init <site>/<command>`.
- Added public package exports for the hosted core-command capability contract.

### Fixes
- **Breaking:** `webcmd doctor` now exits with code 78 (`CONFIG_ERROR`) when a required readiness check fails. Its stdout report is unchanged, and soft warnings do not affect the exit code.
- Fixed browser runs hanging after popup or download events fired. `waitForEvent('popup')` and `waitForEvent('download')` now resolve correctly, while event-specific timeouts take effect before the outer run timeout.
- `external install` now returns a nonzero exit code when installation fails.
- External CLI registrations using explicit executable paths are now detected without an unnecessary `PATH` lookup.

### Adapters
- Hosted mode can run Cloud-advertised adapter workflows including `validate`, `verify`, `convention-audit`, `adapter status`, and `adapter reset`.
- Added the public `@agentrhq/webcmd/adapter-analysis` export for platform-neutral adapter validation and convention auditing.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7)

## [0.7.9](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.8...webcmd-v0.7.9) (2026-08-28)

### Highlights
- Hosted mode can now negotiate and run Cloud-advertised core commands for validation, diagnostics, adapter and profile lifecycle management, and plugin catalog listings. Commands appear in help and completion only when supported by the authenticated Cloud manifest.

### Improvements
- Registered external CLIs such as `gh`, `docker`, and user-defined passthrough commands now run in hosted mode. Hosted site commands take precedence when names overlap, arguments such as `--version` are forwarded correctly, and child exit codes are preserved.
- Hosted help and shell completion now include the locally handled `skills` and `update` commands.
- Root-level options such as `--profile`, `--workspace`, and `--session` now route correctly when placed before `skills` or `update`.
- `webcmd profile use` now saves a validated hosted profile preference locally.
- Hosted auth commands now use the same grammar, flags, choices, and help as local auth commands.
- Hosted command listings retain unavailable commands as `LOCAL` entries and return local-only guidance instead of suggesting plugin installation.
- Added public package exports for platform-neutral adapter analysis and the `hosted-core-commands-v1` capability contract.

### Fixes
- `webcmd doctor` now exits with code 78 (`CONFIG_ERROR`) when the daemon, runtime connection, or a performed connectivity check fails. Its stdout report remains unchanged, and soft warnings do not cause failure.
- Failed `webcmd external install` operations now return a nonzero service-unavailable exit code.
- External CLI executable paths containing directory separators are now checked directly instead of using a `PATH` lookup.

### Adapters
- Hosted mode now supports Cloud-advertised adapter validation, verification, convention auditing, status, and reset workflows.
- Adapter analysis can now validate trusted hosted command inventories and audit adapter source conventions without local registry discovery.
- Convention auditing now prevents manifest source paths from escaping the project root and avoids treating unrelated object literals as emitted adapter rows.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7)

## [0.7.8](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.7...webcmd-v0.7.8) (2026-08-27)

### Highlights
- Browser Sessions now use readable, Profile-scoped IDs. Creating a Session requires a name, which is normalized and given a two-character suffix—for example, `webcmd --profile work session create "Work Project"` may return `work-project-k7`.
- Raw browser commands require an explicit readable Session selector at the root, such as `webcmd --profile work --session work-project-k7 browser tabs`.
- Adapter commands without `--session` now consistently reuse the Profile’s fixed `adapter-default` Session.
- Opaque Session IDs and cross-Profile owner discovery have been removed. Continue using the same Profile and immutable ID throughout a Session’s lifetime.

### Improvements
- Updated the CLI reference, troubleshooting guidance, agent documentation, and generated skills for the new Session workflow.

### Contributors
[@rishabhraj36](https://github.com/rishabhraj36)

## [0.7.7](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.6...webcmd-v0.7.7) (2026-08-26)

### Improvements
- Added `webcmd artifact download <download-url> --output <local-path>` for authenticated downloads of hosted execution artifacts. Download URLs are restricted to the configured Webcmd Cloud API origin to prevent credentials from being sent elsewhere.
- Published the full 100-task BU Bench V1 report, including accuracy, token usage, estimated controller cost, agent turns, category results, methodology, limitations, and reproduction steps.

### Fixes
- Hosted Cloud failures with object-valued `error.details` now preserve their original error code and include those details in the CLI error envelope instead of being reported as `HOSTED_PROTOCOL`.
- Site-memory writes on Windows now retry transient `EPERM` errors when creating lock files.

### Adapters
- Hosted `webcmd browser init <site>/<command>` and `webcmd browser verify <site>/<command>` now use the dedicated authoring route and no longer require—or accept—`--session`.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@beubax](https://github.com/beubax)

## [0.7.6](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.5...webcmd-v0.7.6) (2026-08-24)

### Highlights
- Added a published programmatic hosted runner through the new `./hosted/programmatic` package export, enabling Webcmd Cloud and other hosted integrations to invoke Webcmd directly.
- Added virtual in-memory file, stdin, and stdout handling for hosted runs while preserving real-filesystem security protections.
- Webcmd packages now include MCP-oriented skill documents covering usage, smart search, browser workflows, adapter authoring and repair, and sitemap workflows.

### Contributors
[@ngaurav](https://github.com/ngaurav)

## [0.7.5](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.4...webcmd-v0.7.5) (2026-08-24)

### Improvements
- Standardized output formatting across built-in command leaves. `-f/--format` and `--json` are now consistently accepted, and action commands return structured results when a machine-readable format is requested.
- Expanded `browser run` guidance with examples for navigation, uploads, downloads, popups, data URLs, and sandbox limits. Empty runs now warn when they capture no result, logs, artifacts, or snapshot changes, and Node-only `require`/`fs` attempts return actionable guidance.
- Clarified that `webcmd plugin search` searches the installable plugin catalog—not the web. Results now include catalog metadata, and empty results suggest an appropriate `webcmd web fetch` command for web research.
- `webcmd plugin install <name>` now resolves exact catalog matches to their real `installSource`, or directs you to `webcmd plugin search` when no exact match is available.
- Reduced startup noise for help and machine-readable built-in output by suppressing maintenance, update, and compatibility-shim messages on those paths. Plugin startup hooks still run during actual plugin command execution.
- Added `WEBCMD_DAEMON_PORT` support for configuring the daemon port, with invalid values falling back to port 9777.
- Updated agent guidance to use `webcmd web fetch --url <url>` before browser escalation or non-Webcmd HTTP clients. Browser fallback remains gated on `FETCH_BLOCKED` or `FETCH_REQUIRES_BROWSER`.
- Refreshed the Pi BU Bench report and reproducibility instructions. The benchmark harness now also supports browser-use, agent-browser, and playwright-cli against dedicated CloakBrowser sessions.

### Fixes
- Standardized common CLI usage failures—including unknown commands or options, missing arguments or required options, excess arguments, and invalid arguments—to exit with code 2. Explicit JSON or YAML requests now receive one structured error envelope; human output receives one error with relevant help.
- Unknown commands now suggest nearby registered commands and canonical alternatives, such as `webcmd adapters` → `webcmd adapter` and `webcmd fetch` → `webcmd web fetch`. Unknown namespace subcommands also list valid choices without writing misleading help output to stdout.
- Fixed duplicate usage-error output in hosted mode and aligned hosted subcommand lists with local CLI behavior.
- `session close` now accepts either `webcmd session close <session-id>` or the root `--session <session-id>` selector. Closing an unknown or already-closed Session is idempotent, while malformed IDs still return a usage error.
- Cross-Profile Session lookups now identify the owning Profile and provide an exact retry command. Cross-Profile closes are no longer incorrectly reported as already completed, and `session list` displays its Profile scope.
- Download wait timeouts no longer encourage callers to invent file contents. They now recommend saving the actual download event with `download.saveAs(download.suggestedFilename())`, or reporting that no event occurred.
- Popup and new-tab waits now use a short default timeout and provide safer recovery guidance using `context.newPage()` rather than navigating the opener. Diagnostics also explain that Chrome blocks top-level `data:` popups even when `window.open()` returns a Window object.
- Raw observation text now redacts Basic, Negotiate, and NTLM authorization credentials in addition to Bearer tokens.

### Adapters
- Added `webcmd reddit draft-comment`, which opens a Reddit post and inserts text into a fresh, persistent visible composer without submitting the comment.
- Added `--raw` to `webcmd web fetch` for retrieving the original response body, supporting CSS selector discovery, meta tags, and inline script inspection. Raw output reports byte length and explicit truncation metadata while preserving existing fetch safety and challenge handling.
- Improved adapter repair guidance for `EMPTY_RESULT`, selector failures, and related errors. JSON error envelopes now direct users to `webcmd adapter path <site>/<command>`, the `webcmd-autofix` skill, and `--trace retain-on-failure` instead of suggesting login or an unrelated API.
- `webcmd adapter path` now accepts either `site/command` or two positional tokens, such as `webcmd adapter path quotes list`.
- Hardened the REST Countries adapter’s handling of retired v3.1 responses. Deprecation envelopes are now reported as command execution failures with adapter-repair guidance rather than empty results.
- Improved local adapter discovery by detecting runtime imports instead of matching call-like source text. Adapter load failures now surface their file and cause, and `adapter status` reports failed files. `cli()` is the supported adapter-authoring entry point.
- Clarified adapter authoring workflows across `browser init`, `adapter override`, `adapter path`, plugin scaffolds, and site-memory commands, including when to create a private adapter versus override an installed command.
- Added descriptions, argument and option guidance, examples, grammar notes, and structured YAML/JSON help throughout the `webcmd site` command tree.

### Contributors
[@Agnik47](https://github.com/Agnik47) | [@ankitranjan7](https://github.com/ankitranjan7) | [@arzaanxeng](https://github.com/arzaanxeng) | [@beubax](https://github.com/beubax) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.7.4](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.3...webcmd-v0.7.4) (2026-08-19)


### ⚠ BREAKING CHANGES

* **cli:** `webcmd browser fork` is removed. Use `webcmd adapter override <site>/<command>`.

### Features

* add structured output to report and status built-ins ([#306](https://github.com/agentrhq/webcmd/issues/306)) ([0ee02ce](https://github.com/agentrhq/webcmd/commit/0ee02ce432ed45d866c6b7ace6d2bcbf22cebcc3))
* **cli:** add -f/--format to browser verify ([2dc8ae0](https://github.com/agentrhq/webcmd/commit/2dc8ae0ccd39994bac4e2de795d8e58f4a6feef3))
* **cli:** add -f/--format to browser verify ([#351](https://github.com/agentrhq/webcmd/issues/351)) ([ccfc04f](https://github.com/agentrhq/webcmd/commit/ccfc04f022ffbc499722ac5cb60e3fe31a319de9))


### Bug Fixes

* **browser:** decode response bodies as UTF-8 text in the run sandbox ([#357](https://github.com/agentrhq/webcmd/issues/357)) ([65d31cd](https://github.com/agentrhq/webcmd/commit/65d31cd78a3eabc15d2872b77028517d1692f2b7))
* **browser:** don't reuse a dead page/context lease in browser run ([#324](https://github.com/agentrhq/webcmd/issues/324)) ([ef4fda7](https://github.com/agentrhq/webcmd/commit/ef4fda76c321cba3efcb70ca428ffc1b0158488d))
* **browser:** report the caller's line and column for browser-run compile errors ([#356](https://github.com/agentrhq/webcmd/issues/356)) ([44f1c5f](https://github.com/agentrhq/webcmd/commit/44f1c5f64d07c24cdd13d8c9581005648f16cc4f))
* **cli:** fail validate on unknown target instead of PASS ([#366](https://github.com/agentrhq/webcmd/issues/366)) ([5d8e289](https://github.com/agentrhq/webcmd/commit/5d8e28988211791670d6b778f03b0e18a46590d7))
* **cli:** honour -f json on the error envelope ([#368](https://github.com/agentrhq/webcmd/issues/368)) ([bc102a9](https://github.com/agentrhq/webcmd/commit/bc102a980e501e4b4cbbd6ffa4e5060fb2eed4cd))
* **cli:** never prompt in webcmd setup when stdin is not a TTY ([#369](https://github.com/agentrhq/webcmd/issues/369)) ([51eb2d1](https://github.com/agentrhq/webcmd/commit/51eb2d10137cd729e25353fb513aa03e3177baa3))
* **cli:** reject unknown profile use instead of poisoning the default ([#367](https://github.com/agentrhq/webcmd/issues/367)) ([2419b01](https://github.com/agentrhq/webcmd/commit/2419b01b2f1e6c6dce37396aa520ac93c21d4b54))
* **cli:** remove browser fork, add adapter override to hosted mode ([#361](https://github.com/agentrhq/webcmd/issues/361)) ([3919f6f](https://github.com/agentrhq/webcmd/commit/3919f6fe678878c9ab802ab772dc5f75f198ecea))
* **cli:** report built-in command errors instead of crashing ([#363](https://github.com/agentrhq/webcmd/issues/363)) ([ef149b1](https://github.com/agentrhq/webcmd/commit/ef149b145b41c5a1034cd6798c9a3f6f85d4675c))
* **cli:** unknown flags exit 2 and list valid flags ([#370](https://github.com/agentrhq/webcmd/issues/370)) ([9cd0d5a](https://github.com/agentrhq/webcmd/commit/9cd0d5a453fe4718604443214e04203090fb5da7))
* **download:** isolate temp files and reject duplicate download targets ([#333](https://github.com/agentrhq/webcmd/issues/333)) ([4c9c322](https://github.com/agentrhq/webcmd/commit/4c9c322963c1048a4b88301081c787c167d9f24a))
* **local-cloak:** honour waitUntil when opening a tab with a url ([#316](https://github.com/agentrhq/webcmd/issues/316)) ([5a65936](https://github.com/agentrhq/webcmd/commit/5a659367c37c06ad00881068ff27576547a993bf))
* make -v effective in hosted, browser, and auth commands ([#315](https://github.com/agentrhq/webcmd/issues/315)) ([7a72596](https://github.com/agentrhq/webcmd/commit/7a72596d8c3e4166f1877cab3271a80edc7279d2))
* **site-memory:** lock site memory writes across processes ([#321](https://github.com/agentrhq/webcmd/issues/321)) ([a740cbe](https://github.com/agentrhq/webcmd/commit/a740cbe3b08379ab08c61a59f9f81da1729398f1))


### Miscellaneous Chores

* release 0.7.4 ([bb6f7b3](https://github.com/agentrhq/webcmd/commit/bb6f7b3257820034b168f875998fe924b3512fff))

## [0.7.3](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.2...webcmd-v0.7.3) (2026-08-18)

### Improvements
- `webcmd profile list` now supports `-f, --format` for structured output.
  - Saved but disconnected profiles are included with their connection status.
  - Structured output now reports `DAEMON_UNAVAILABLE` instead of returning an empty list when the daemon is stopped or stale.
- Expanded browser skill guidance to clearly describe the `browser run` QuickJS sandbox, including available globals, DOM access through `page.evaluate()`, file uploads, blocked APIs, and local/hosted behavior.
- Updated file-upload examples to use the supported `TextEncoder` with `Uint8Array` payloads.

### Fixes
- Added standard encoding APIs to the `browser run` sandbox: `btoa`, `atob`, `TextEncoder`, and `TextDecoder`.
- Unsupported Playwright API errors now suggest supported alternatives where available, such as using `webcmd session close`, creating a new session, using `page.request`, or driving the page without raw CDP.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@ngaurav](https://github.com/ngaurav) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.7.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.1...webcmd-v0.7.2) (2026-08-18)


### Bug Fixes

* **browser:** default every daemon command to a background window ([#328](https://github.com/agentrhq/webcmd/issues/328)) ([40a7b82](https://github.com/agentrhq/webcmd/commit/40a7b82213174ef845f015a8c1c1a2c14334cbc5))
* **browser:** tolerate pages closing during session cleanup ([#329](https://github.com/agentrhq/webcmd/issues/329)) ([87131f5](https://github.com/agentrhq/webcmd/commit/87131f503b1c5d1a0b30b4d06a88f942fd35a89a))

## [0.7.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.7.0...webcmd-v0.7.1) (2026-08-14)

### Improvements
- Expanded Webcmd Cloud parity with mutable `input-output` file arguments and corrected filename mapping for commands that produce multiple files.
- Added hosted support for `browser init`, `browser verify`, adapter source management, and site-memory workflows, enabling adapter authoring and validation in hosted environments.
- Added marketplace availability metadata to distinguish `hosted`, `mixed`, and `local-only` plugins.

### Fixes
- Improved `webcmd doctor` browser diagnostics:
  - Browser installation now completes before the timed connectivity probe begins, preventing first-use downloads from being reported as 8-second browser command timeouts.
  - A dedicated **Browser binary** status identifies missing, invalid, or non-executable Chromium binaries separately from daemon/runtime connectivity.
  - Missing binaries now report their expected path, download URL, and actionable `CLOAKBROWSER_BINARY_PATH` guidance.
- On macOS, Webcmd now repairs stale LaunchServices registrations for managed Chromium bundles and retries background launch once. If remediation fails, `doctor` displays the exact manual `lsregister` command.
- Prevented background Chromium profiles on macOS from crashing after `webcmd doctor` closes its probe window.
- Fixed persistent browser Sessions so `browser run` cannot access pages owned by sibling Sessions.

### Adapters
- Added hosted file contracts across the official plugin catalog, including support for mutable files and commands with multiple outputs.
- Removed local-only filesystem and binary assumptions from affected plugin commands to improve hosted execution compatibility.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@ayushsingh82](https://github.com/ayushsingh82) | [@beubax](https://github.com/beubax) | [@Sarfraz-droid](https://github.com/Sarfraz-droid)

## [0.7.0](https://github.com/agentrhq/webcmd/compare/webcmd-v0.6.2...webcmd-v0.7.0) (2026-08-14)

_webcmd v0.7.0: The Multiverse of Agents Is Here._

### Highlights

Webcmd 0.7.0 is the multi-agent browser runtime release.

Browser work is no longer organized around one shared window. Agents can create explicit, persistent Sessions inside a profile, work concurrently in isolated Cloak windows, carry authentication state safely, recover stale leases, and close their workspaces deterministically. Authentication handoffs are scoped to the Session that started them, so humans can complete login, MFA, or CAPTCHA challenges without one agent disrupting another.

```bash
webcmd --profile work session create
webcmd --session session_abc browser run --stdin
webcmd --session session_abc browser snapshot --snapshot-mode read
webcmd session list
webcmd session close session_abc
```

The agent multiverse now extends across development environments. Webcmd adds a native Claude Code plugin marketplace alongside Codex, carrying the same seven bundled authoring and browser skills. Onboarding was rewritten across Claude Code, Codex, Cursor, Hermes, OpenCode, OpenClaw, and Pi so agents can install Webcmd, understand which existing tools to keep, and route compatible browser work through one deterministic command surface.

Research workflows also become agent-native. The new OmniSearch plugin searches seven public communities without login, while Smart Search now recognizes site-specific requests and goes directly to an installed adapter instead of wasting time on generic search engines.

### Improvements

- Added explicit browser Sessions with `session create`, `session list`, and `session close`, plus the root-level `--session` selector. Agents sharing one profile can now work concurrently in separate browser workspaces. [#291](https://github.com/agentrhq/webcmd/pull/291)
- Added session isolation across Cloak windows, browser actions, dialogs, adapter execution, authentication handoffs, leases, cancellation, and daemon disconnects.
- Brought the Session model to hosted browser execution with local/hosted contract and command parity.
- Made `web fetch` a client-owned core command. It now follows a deterministic HTTP-only ladder before any explicit browser fallback: plain HTTP, Chrome TLS impersonation, then Firefox TLS impersonation.
- Added a site-named fast path to Smart Search. Requests naming Hacker News, Reddit, or another supported site now try that site's adapter before a generic search engine. [#269](https://github.com/agentrhq/webcmd/pull/269)
- Improved plugin search so spaced, hyphenated, punctuated, concatenated, and reordered multi-word queries can find the intended plugin while still requiring every search term. [#285](https://github.com/agentrhq/webcmd/pull/285)
- Added a native Claude Code marketplace and synchronized Claude Code, Codex, and npm package version metadata. [#273](https://github.com/agentrhq/webcmd/pull/273)
- Streamlined copyable onboarding prompts and restored the manual quick start for users who prefer direct CLI installation. [#272](https://github.com/agentrhq/webcmd/pull/272) [#275](https://github.com/agentrhq/webcmd/pull/275)
- Reworked tool-routing guidance across seven agent harnesses. Webcmd now distinguishes tools that should be replaced from native search or development tools that should remain available.
- Made plugin updates ignore only untracked npm-generated artifacts such as `node_modules` and `package-lock.json`, while continuing to protect genuine user changes. [#267](https://github.com/agentrhq/webcmd/pull/267)
- Added an explicit confirmation boundary before promoting private adapters into the public repository, plus CI protection against unrelated changes in new-plugin pull requests. [#234](https://github.com/agentrhq/webcmd/pull/234) [#304](https://github.com/agentrhq/webcmd/pull/304)
- **Breaking:** invalid `-f` or `--format` values now fail consistently with exit code 2 instead of silently falling back to a table. Supported formats are `table`, `plain`, `json`, `yaml`, `md`, and `csv`. [#190](https://github.com/agentrhq/webcmd/pull/190)

### Fixes

- Enforced `web fetch --timeout` across the complete request lifecycle, including proxy teardown, DNS resolution, keep-alive tunnels, and late socket errors. A timed-out request now exits at its declared deadline with a structured `TIMEOUT` error. [#265](https://github.com/agentrhq/webcmd/pull/265)
- Fixed browser-run commands returning JavaScript `undefined`; deterministic output now serializes it as `null`. [#278](https://github.com/agentrhq/webcmd/pull/278)
- Repaired `webcmd doctor` session cleanup and first-window selection so diagnostic probes do not leak into normal browser work. [#298](https://github.com/agentrhq/webcmd/pull/298)
- Made the verify row-shape top-level key limit configurable for commands with legitimately wide structured output. [#230](https://github.com/agentrhq/webcmd/pull/230)
- Restored 44 browser test files containing 596 tests to CI coverage, and made the Playwright vendor digest stable across Windows and POSIX paths. [#238](https://github.com/agentrhq/webcmd/pull/238)
- Replaced a real 31 MB test write with a sparse file, preserving coverage while avoiding Windows CI timeouts. [#268](https://github.com/agentrhq/webcmd/pull/268)
- Corrected plugin promotion documentation, repository paths, community-sync guidance, and Hermes formatting.

### Adapters

- Added **OmniSearch**, a no-login research plugin spanning Hacker News, Stack Overflow, GitHub, arXiv, Dev.to, Lobsters, and Bluesky. Its `research` command aggregates evidence, while `verdict` distills community reception for agent workflows. [#270](https://github.com/agentrhq/webcmd/pull/270)

```bash
webcmd omnisearch research "browser agents" -f json
webcmd omnisearch verdict "browser agents" -f json
```

- Added `youtube frames` for capturing timestamped PNG frames at exact timestamps or evenly across a video. [#297](https://github.com/agentrhq/webcmd/pull/297)

```bash
webcmd youtube frames "<video-url>" --timestamps 30,90,150
webcmd youtube frames "<video-url>" --count 5
```

- Added authenticated Amazon India cart inspection and guarded cart additions, including explicit product-variant verification. [#241](https://github.com/agentrhq/webcmd/pull/241)

```bash
webcmd amazon-in cart
webcmd amazon-in cart-add
```

### Contributors

[@adot-7](https://github.com/adot-7) | [@Agnik47](https://github.com/Agnik47) | [@ankitranjan7](https://github.com/ankitranjan7) | [@anshula-100](https://github.com/anshula-100) | [@ayushsingh82](https://github.com/ayushsingh82) | [@beubax](https://github.com/beubax) | [@ngaurav](https://github.com/ngaurav) | [@Rishet11](https://github.com/Rishet11) | [@rishabhraj36](https://github.com/rishabhraj36) | [@Sneh30](https://github.com/Sneh30) | [@yashkhatri012](https://github.com/yashkhatri012)

## [0.6.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.6.1...webcmd-v0.6.2) (2026-08-12)

### Highlights
- Added explicit browser Sessions for local and hosted browser workflows.
- Added the `browser run` code executor path, including hosted routing and file transfer support.
- Moved CLI surfaces into plugins, with marketplace search/install and command discovery metadata.
- Added plugin override precedence and reconciliation: local `~/.webcmd/clis` overrides installed plugins, update detection is content-based, and override status is actionable.
- Expanded Webcmd Cloud parity for browser commands, hosted manifests, profiles/workspaces, auth handoff, and verify fixture evaluation.

### Fixes
- Hardened session admission/cancellation, background tab focus, Cloak process matching, and browser run timeout behavior.
- Fixed plugin discovery/install edge cases, adapter status output, hosted output flushing, and local override reconciliation.
- Restored and hardened adapter behavior across Amazon, Facebook, Twitter, TikTok, YouTube, and others.

## [0.6.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.6.0...webcmd-v0.6.1) (2026-08-12)

### Highlights
- Added explicit raw browser Sessions for parallel agents.
- Kept adapter commands on an adapter-default Session unless `--session` is supplied.
- Isolated local Cloak Session windows and pages, and fixed page/admission partitioning by adapter site.
- Scoped auth handoff and Session close behavior so active work is not interrupted.
- Updated bundled documentation and skills for Session usage.

## [0.6.0](https://github.com/agentrhq/webcmd/compare/webcmd-v0.5.4...webcmd-v0.6.0) (2026-08-10)

_webcmd v0.6.0: Code Is All You Need._

### Highlights
Webcmd 0.6.0 is the plugin architecture release. Site CLIs now live as independently installable plugins instead of being bundled into the core package, so the CLI runtime can stay small while adapters evolve on their own cadence. Agents should search the catalog first with `webcmd plugin search <site> -f json`, then install the returned `installSource`.

The new browser-run executor turns browser automation into code. `webcmd browser <session> run` executes sandboxed Playwright-style JavaScript against a real Webcmd browser session, letting agents inspect pages, reuse state, collect artifacts, and verify UI behavior without hand-assembling brittle one-off commands.

Plugin overrides are safer and more deterministic. Local command overrides in `~/.webcmd/clis` take precedence over installed plugin commands, override update detection is content-based, and installing a newly added monorepo sub-plugin refreshes stale local catalog state instead of incorrectly reporting that the plugin does not exist.

### Improvements
- Added `webcmd update` to upgrade the CLI and refresh linked skills from one command.
- Added `webcmd adapter override <site>/<command>` for forking an installed plugin command into an editable local override.
- Moved the core `web` adapter into the new command layout and kept fetch/read workflows available through the same runtime surface.
- Reworked agent onboarding docs around the new plugin-first flow, including Codex, Claude Code, Cursor, Hermes, OpenCode, Pi, OpenClaw, and custom SDK setup.
- Migrated enhanced release-note generation to OpenAI-backed tooling and hardened the structured docs-review flow.

### Fixes
- Fixed stale monorepo plugin installs so a new sub-plugin added to `agentrhq/webcmd` can be found and installed without manually refreshing local cache state.
- Repaired adapter drift and markdown/console output escaping issues across affected site commands.
- Hardened docs-review parsing for fenced JSON and switched it to a lighter review model.
- Hosted browser responses now tolerate additional cloud fields such as `expiresAt`.
- Cached browser runtime version checks to make status and doctor-style commands faster.

### Adapters
- All site adapters now install through the plugin catalog instead of shipping inside the npm package.
- Added postgraduate course export plugins for University of Cincinnati, Concordia University, University of Gottingen, Heidelberg University, HFT Stuttgart, Illinois Institute of Technology, Johns Hopkins University, University of Alberta, and Yale University.
- Added a `luma` plugin for events, guests, and registration-question workflows.
- Updated Skyscanner docs with required flags and current examples.
- Moved and repaired web/social adapter coverage touched by the plugin migration, including Amazon, Facebook, TikTok, Twitter/X, and the built-in web fetch commands.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@anshula-100](https://github.com/anshula-100) | [@askadityapandey](https://github.com/askadityapandey) | [@beubax](https://github.com/beubax) | [@ngaurav](https://github.com/ngaurav) | [@rajarshidattapy](https://github.com/rajarshidattapy) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.5.4](https://github.com/agentrhq/webcmd/compare/webcmd-v0.5.3...webcmd-v0.5.4) (2026-08-09)

### Highlights
- All site adapters are now independent plugins and are no longer bundled with the core `webcmd` package. This major architectural change allows adapters to be updated individually without requiring a new `webcmd` release. Previously bundled commands can be installed using `webcmd plugin install github:agentrhq/webcmd/plugins/<site-name>`. (#216)

### Improvements
- A new `webcmd update` command allows you to upgrade `webcmd` to the latest version and refresh bundled skill links directly from the CLI. (#224)
- The new `webcmd adapter override <site>/<command>` command lets you create a local, editable copy of a command from an installed plugin, making it easier to customize or iterate on existing adapters. (#245)
- The `browser run` command now uses a sandboxed Playwright environment, improving the reliability and capability of browser-based automations. (#196)
- Documentation has been updated to:
    - Add the `webcmd skills` subcommands to the CLI reference. (#200)
    - Document the `-f plain` output format and aliases for `yaml` and `md`. (#202)
    - Improve the clarity and correctness of the main README file. (#205, #207)

### Fixes
- Hosted browser commands will no longer fail when the Webcmd Cloud API includes an `expiresAt` field in its response. (#194)
- Improved the performance of status-checking commands like `webcmd doctor` by caching the browser runtime version, reducing unnecessary file reads. (#213)

### Adapters
- Nine new adapters have been added for exporting postgraduate course data from the following universities: University of Cincinnati, Concordia University, University of Göttingen, Heidelberg University, HFT Stuttgart, Illinois Institute of Technology, Johns Hopkins University, University of Alberta, and Yale University. (#192)
- A new `luma` adapter allows you to manage Luma events, guests, and registration questions. (#195)
- The documentation for the `skyscanner` adapter has been updated to include required flags and provide current examples. (#209)

### Reverts
- Reverted the addition of the one-click "Copy prompt" feature for AI agent setup from the documentation homepage. (#221)

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@askadityapandey](https://github.com/askadityapandey) | [@beubax](https://github.com/beubax) | [@rajarshidattapy](https://github.com/rajarshidattapy) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.5.3](https://github.com/agentrhq/webcmd/compare/webcmd-v0.5.2...webcmd-v0.5.3) (2026-08-03)

### Fixes
- Keep the local Cloak wrapper on `0.4.5`, which targets the latest free stealth Chromium release (`146.0.7680.177.5`) on supported platforms.

### Contributors
[@beubax](https://github.com/beubax)

## [0.5.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.5.1...webcmd-v0.5.2) (2026-07-31)

### Improvements
-   Commands running in the background will no longer cause the browser window to steal focus.

### Adapters
-   **District**: Fixed an issue where the `district/login` command could fail to open the site's login modal. The command is now more resilient to site loading delays.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@beubax](https://github.com/beubax)

## [0.5.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.5.0...webcmd-v0.5.1) (2026-07-30)

### Adapters
*   The `district checkout` adapter now automatically proceeds to the payment page to open the UPI QR scanner. A new `--payment` argument can be set to `review` to stop on the order review page instead. New output columns have been added to report payment status (`paymentMethod`, `paymentState`, `upiQrVisible`, `paymentAmount`).
*   The seat selection logic for the `district checkout` adapter has been hardened to handle cases where the site hides selected seat labels, making the command more reliable.

### Contributors
[@beubax](https://github.com/beubax)

## [0.5.0](https://github.com/agentrhq/webcmd/compare/webcmd-v0.4.3...webcmd-v0.5.0) (2026-07-30)

_webcmd v0.5.0: A Native Codex Plugin and Expanded Discovery_

### Highlights
Webcmd is now available as a native plugin for Codex. In Codex, open **Plugins**, choose **Add plugin marketplace**, and enter `agentrhq/webcmd` to find and install the new plugin. It bundles all seven core Webcmd skills for a seamless agent setup and, on first use, will help install the Webcmd CLI if it is missing.

### Improvements
- The `smart-search` skill has been updated with improved guidance, helping agents make better use of Webcmd's expanding set of search adapters.

### Fixes
- `webcmd doctor` no longer brings the browser window to the foreground on startup, respecting the background window mode.
- Verbose logging is now correctly disabled when the `WEBCMD_VERBOSE` environment variable is set to `0`, `false`, or other "false-y" values.

### Adapters
- A new `pypi` adapter has been added to inspect public Python package metadata. Use `webcmd pypi package <name>` for project details and `webcmd pypi releases <name>` to list recent release files.
- The new `web fetch` command provides a fast, non-browser way to retrieve the content of a URL.
- The browser-based `web read` command has been renamed to `web fetch-browser` to distinguish it from the new non-browser fetch command.
- Over 70 existing commands have been tagged as `search` adapters, improving command discovery and the effectiveness of the `smart-search` skill.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@beubax](https://github.com/beubax) | [@ngaurav](https://github.com/ngaurav) | [@Savyasachi-2005](https://github.com/Savyasachi-2005) | [@yoldaolmak](https://github.com/yoldaolmak)

## [0.4.3](https://github.com/agentrhq/webcmd/compare/webcmd-v0.4.2...webcmd-v0.4.3) (2026-07-27)

### Improvements
*   Browser-based commands now run in a background window by default. Use the `--window foreground` flag to show a visible browser for interactive workflows.

### Adapters
*   **ChatGPT**: The `chatgpt model` command adds support for selecting the `GPT-5.6 Pro` model.
*   **Google**: Adds the new `google images` command to perform public, browser-based image searches.
*   **Instagram**: The `instagram user` command can now fetch a user's feed directly by username.
*   **Trip.com**: Adds a new `trip` adapter with twelve commands for searching flights, hotels, attractions, trains, cars, packages, and deals.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7)

## [0.4.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.4.1...webcmd-v0.4.2) (2026-07-27)

### Improvements
*   **Workspace-Scoped Profiles for Webcmd Cloud**: Hosted commands can now be scoped to a workspace using the new `--workspace <id>` flag or the `WEBCMD_WORKSPACE` environment variable. This allows for better isolation of user data, especially in multi-tenant applications. Within a workspace, profiles are created lazily on first use.
*   **Simplified Hosted Profile Management**: The `webcmd profile` command for hosted mode has been simplified. It now only supports `list` and `delete` subcommands, as profile creation is now handled automatically within the ambient workspace.

### Adapters
*   **Amazon India (`amazon-in`)**: Adds a new adapter for Amazon.in with support for product search, viewing product details, managing wishlists, and a guarded checkout process. New commands include `amazon-in search`, `product`, `wishlist`, `login`, `whoami`, `checkout`, and `checkout-status`.
*   **BMWBLOG (`bmwblog`)**: Adds a new read-only adapter to search and read articles from BMWBLOG. New commands are `bmwblog latest`, `search`, and `article`.
*   **TechCrunch (`techcrunch`)**: Adds a new read-only adapter for TechCrunch. New commands `techcrunch search` and `article` allow you to find and read the latest tech news.
*   **Y Combinator (`ycombinator`)**: Adds a new read-only adapter for browsing the Y Combinator startup directory. New commands include `ycombinator companies` to search for startups and `ycombinator company` to view a specific company's profile.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@beubax](https://github.com/beubax)

## [0.4.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.4.0...webcmd-v0.4.1) (2026-07-24)

### Highlights
- **Hosted Profile Management**: The `webcmd profile` command now manages hosted browser profiles in Webcmd Cloud.
  - Create named profiles with `webcmd profile create <name>`. You can also associate a public external user ID using the `--user-id` flag.
  - View profiles with `webcmd profile list` and `webcmd profile get <selector>`. Profiles can be looked up by their immutable ID, name, or external user ID.
  - Delete profiles with `webcmd profile delete <id>`. Deletion requires the profile's immutable ID to prevent accidental data loss.
  - Unlike in local mode, custom hosted profiles must be created before use. An unknown `--profile` selector will fail instead of creating a new profile on the fly.

### Contributors
[@beubax](https://github.com/beubax)

## [0.4.0](https://github.com/agentrhq/webcmd/compare/webcmd-v0.3.4...webcmd-v0.4.0) (2026-07-23)


### Features

* add grayscale color palette variables to root stylesheet ([7fc2b0a](https://github.com/agentrhq/webcmd/commit/7fc2b0ae3a8b6777a5c7b4e812241569de0e4df2))
* add local auth handoff protocol ([ea93b63](https://github.com/agentrhq/webcmd/commit/ea93b630a1835fbd65478ae28050a714ca770510))
* enhance screenshot functionality to restore viewport size and support CDP overrides ([0ba71d6](https://github.com/agentrhq/webcmd/commit/0ba71d66dcfebde9d0ab70d1ecb8491ec417e714))
* enhance screenshot functionality to restore viewport size and support CDP overrides ([6caae1b](https://github.com/agentrhq/webcmd/commit/6caae1b8924da5f5821a21db7f31fa2d9fe5d128))
* return local login handoffs immediately ([9749f3f](https://github.com/agentrhq/webcmd/commit/9749f3fcef5ea9a65f0312d8edb52be956b61bb0))
* update documentation theme with custom styling, typography, and site logo ([b51153b](https://github.com/agentrhq/webcmd/commit/b51153b6e5559c3a2f545853844b00a8ba4261a2))


### Bug Fixes

* condition autofix auth handoff ([423966e](https://github.com/agentrhq/webcmd/commit/423966ed2232db915184fd0f8c5990d7f8bbeb84))
* **docs:** show navigation logo ([bffe1e5](https://github.com/agentrhq/webcmd/commit/bffe1e5f49856f2515f477ca78b57c2a48865f40))
* **docs:** show navigation logo ([1b9fad7](https://github.com/agentrhq/webcmd/commit/1b9fad74fe0e343c6e193f644090a8b47416c36b))
* harden local auth handoff ([f08ce77](https://github.com/agentrhq/webcmd/commit/f08ce7702c64a8b507e7eca299052e5683cfb462))
* keep auth handoff skills mode neutral ([60dc2f5](https://github.com/agentrhq/webcmd/commit/60dc2f58c7d38a7d459d69260464261463bfcba5))
* keep pack JSON stdout clean ([087a398](https://github.com/agentrhq/webcmd/commit/087a3984c155f1fb577bbb5b3dff002cb9cf5353))
* normalize Hacker News job URLs ([98ca921](https://github.com/agentrhq/webcmd/commit/98ca921a177a046594df9fe28c4688647fe71c4e))
* require auth handoff verification ([79fc72f](https://github.com/agentrhq/webcmd/commit/79fc72fe9d5cc900be456b3548c2546ea6a3677b))

## [0.3.4](https://github.com/agentrhq/webcmd/compare/webcmd-v0.3.3...webcmd-v0.3.4) (2026-07-17)

### Improvements
*   The accessibility tree snapshot now reveals actionable elements even when their parent containers are ignored by assistive technologies, providing a more complete view of the page.
*   Documentation has been updated with safer patterns for adapter discovery, recommending that users filter the `webcmd list` command to prevent incomplete results from truncated output.
*   Accessibility snapshot helpers are now exported for developers using `webcmd` as a library.

### Fixes
*   The accessibility tree snapshot is now more robust and will no longer hang when processing malformed pages that contain cycles or very deep chains of ignored elements.

### Contributors
[@beubax](https://github.com/beubax)

## [0.3.3](https://github.com/agentrhq/webcmd/compare/webcmd-v0.3.2...webcmd-v0.3.3) (2026-07-16)

### Highlights
*   Skill management has been improved with new and renamed commands. Use `webcmd skills add` (formerly `install`) to add bundled skills to your agent environment, and the new `webcmd skills remove` to safely remove them.

### Improvements
*   Browser sessions are now more robust. `webcmd` can recover sessions after an unexpected closure and will prevent multiple commands from writing to the same persistent session at the same time. Blocked commands will now exit with a status code of 75 to signal that the session is busy.
*   Commands can now be authored with `freshPage: true` metadata, allowing them to run in a new, clean browser tab while preserving an existing login session.
*   The project's `README.md` now includes prominent links to the full documentation site at [webcmd.dev/docs](https://webcmd.dev/docs).
*   Corrected the adapter authoring documentation for `webcmd browser init` to remove a non-existent `--strategy` flag.

### Fixes
*   The `webcmd doctor` command now correctly reports the installed version of the Cloak browser runtime instead of "version unknown".
*   Local-only commands, such as `webcmd skills`, now run correctly when `webcmd` is configured for hosted (cloud) mode.

### Adapters
*   The `producthunt` adapter now correctly detects and reports security verification pages, preventing commands from failing unexpectedly.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@beubax](https://github.com/beubax) | [@rajarshidattapy](https://github.com/rajarshidattapy)

## [0.3.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.3.1...webcmd-v0.3.2) (2026-07-15)

### Adapters
*   The `spotify` adapter has been restored. All `spotify` commands are now available for use again.
*   The `producthunt hot` command is now more reliable.

### Contributors
[@beubax](https://github.com/beubax)

## [0.3.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.3.0...webcmd-v0.3.1) (2026-07-15)

### Improvements
* The `webcmd plugin create` command now prompts for an author name and GitHub handle to include in the new plugin's metadata.
* The `webcmd-autofix` skill for AI agents has been updated with a workflow to report unresolved, reproducible `webcmd` failures to the development team.

### Fixes
* On macOS, running a browser-based command with `--window background` will no longer bring the browser to the foreground on its first launch.

### Adapters
* **LinkedIn**: Two new adapters have been added:
    * `linkedin company`: Reads a company's profile page for details like industry, size, headquarters, and follower count.
    * `linkedin connections`: Lists your first-degree connections with their names, headlines, and profile URLs.
* **ChatGPT**:
    * `chatgpt deep-research-result`: This command can now report the progress of an ongoing Deep Research task, not just the final completed report.
    * `chatgpt ask`: Improved reliability when waiting for a response to finish generating.
* **Facebook**:
    * `facebook search`: The reliability of the search workflow has been improved.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@beubax](https://github.com/beubax) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.3.0](https://github.com/agentrhq/webcmd/compare/webcmd-v0.2.5...webcmd-v0.3.0) (2026-07-13)

### Highlights
- Introduces a new hosted execution mode, allowing `webcmd` to operate as a thin client against the Webcmd Cloud API. This offloads command execution and browser automation to the cloud service and can be configured with a new `setup` command.

### Improvements
- Agent skill documentation has been updated to improve command discovery and error handling:
  - Adds a fallback to search for installable plugins (`webcmd plugin search`) when a command is not found locally.
  - Clarifies that running `webcmd` with no arguments lists all available commands.
  - Provides better guidance on handling network errors during `webcmd plugin search`, prompting users to retry if a fetch fails.

### Fixes
- The `--window background` flag now correctly prevents browser-backed commands from stealing focus.

### Adapters
- Authentication commands (like `whoami` and `login`) that use the shared site-auth helper now correctly wrap their JSON output in an array, making them compatible with agent workflows expecting structured rows.
- The `antigravity` adapter no longer incorrectly registers itself as an installable agent skill.

### Contributors
[@ankitranjan7](https://github.com/ankitranjan7) | [@beubax](https://github.com/beubax) | [@ngaurav](https://github.com/ngaurav) | [@rishabhraj36](https://github.com/rishabhraj36)

## [0.2.5](https://github.com/agentrhq/webcmd/compare/webcmd-v0.2.4...webcmd-v0.2.5) (2026-07-10)

### Improvements
- Added new commands for plugin discovery and management. Use `webcmd plugin search` to find new community plugins, and `webcmd plugin catalog` subcommands to manage the marketplace sources where `webcmd` searches.
- Documentation has been updated to explain the new plugin monorepo model, where community adapters can be promoted directly into the main repository. This makes them easier to discover and install.

### Adapters
- The BikeWale adapter has been promoted to the main repository as a community plugin.

## [0.2.4](https://github.com/agentrhq/webcmd/compare/webcmd-v0.2.3...webcmd-v0.2.4) (2026-07-10)

### Highlights
- Introduced a plugin marketplace for discovering and installing new adapters. Use the new `webcmd plugin search` command to find available plugins and `webcmd plugin catalog` to manage marketplace sources.

### Fixes
- Fixed failures to launch a browser session when the profile was locked or left in a stale state from a previous run.

### Adapters
- Hardened the `practo login` command to wait for manual sign-in to complete, and added a `--timeout` option.

## [0.2.3](https://github.com/agentrhq/webcmd/compare/webcmd-v0.2.2...webcmd-v0.2.3) (2026-07-09)

### Highlights
- Added four new e-commerce and booking adapters: Blinkit, Zepto, BigBasket, and Practo, enabling automated workflows for groceries, deliveries, and appointments.
- Hardened the District adapter's checkout command to prevent incorrect seat selection, ensuring payment flows are initiated with the exact items requested.

### Improvements
- Introduced a new plugin catalog to support community-developed commands, starting with the `skyscanner` plugin for flight searches.
- The adapter-author skill now provides a more interactive scaffolding experience by asking for user use cases before recommending and generating subsequent commands.
- Improved the release automation workflow to auto-generate more detailed release notes and update the `CHANGELOG.md` file.

### Fixes
None.

### Adapters
- **BigBasket**: Added the `bigbasket` adapter for online grocery shopping, with commands for `search`, `product`, `category`, `add-to-cart`, `cart`, and a review-only `checkout`.
- **Blinkit**: Added a new `blinkit` adapter for grocery delivery, with commands for the full buying path: `login`, `search`, `product`, `add-to-cart`, `cart`, `checkout`, and `place-order`.
- **District**: Hardened the `district checkout` command by adding two new guards. It now reconciles the selected seats with the requested seats to prevent auto-selection of extra tickets, and adds a final assertion on the review page to ensure order accuracy before payment.
- **Practo**: Added a comprehensive `practo` adapter for healthcare appointments. It supports doctor discovery (`search`, `profile`), slot booking (`slots`, `book-preview`, `book-confirm`), and appointment management (`appointments`, `appointment`, `cancel`).
- **Zepto**: Introduced the `zepto` adapter for quick commerce, including commands for `login`, `location`, `search`, `product`, `add-to-cart`, `cart`, `checkout`, and `place-order`.

### Contributors
- @ankitranjan7
- @beubax
- @ngaurav
- @rishabhraj36

### Reverts
None.

## [0.2.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.2.1...webcmd-v0.2.2) (2026-07-09)

### Highlights

- Bundled Webcmd skills are now much easier to add and refresh through `webcmd skills add` and `webcmd skills update`.
- Persistent-session commands gained a cleaner authoring model with `freshPage`, which keeps login/profile state while avoiding stale page state.
- District booking support moved from local-only adapters into the repo.

### Improvements

- Added `freshPage: true` for persistent site-session commands so adapter authors can start from a clean tab without throwing away cookies or profile state.
- Added bundled Webcmd skill installation and update flows for supported agents.
- Repaired the plugin-management e2e test by replacing a deleted test plugin repository with a live plugin repository.
- Refreshed README guidance around the current project positioning.

### Fixes

- Preserved `freshPage` in generated CLI manifests.
- Fixed District output validation so adapter columns such as `number`, `row`, `seat`, and `_score` are not silently dropped.
- Quoted sitemap author skill frontmatter for strict YAML parsers.
- Fixed Reddit popular HTML response handling.

### Adapters

- Promoted the District (`district.in`) movie and event booking adapters into `clis/district`.
- Added and hardened District flows for search, listings, showtimes, seats, checkout, locations, location switching, and auth status checks.
- Hardened District checkout with clean-start sessions, a login gate before seat selection, stale-session refresh, and payment-handoff behavior.
- Added the shared site-auth `openLogin(page)` hook for modal-based login flows such as District.

## [0.2.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.2.0...webcmd-v0.2.1) (2026-07-07)

### Highlights

- Browser profile routing became more forgiving for saved defaults while keeping explicit profile selections strict.
- Twitter adapter output and deletion workflows became more useful and reliable.
- Windows command shim handling was fixed for external CLI passthrough.

### Improvements

- Routed default browser profiles as preferred profiles instead of strict requirements.
- Stabilized headed browser e2e coverage and normalized Cloak profile path expectations.
- Refreshed README positioning, branding, social links, and agent-focused docs.

### Fixes

- Handled Windows `.cmd` shims for external command execution.
- Hardened tweet deletion against delayed page loading, stale menus, and runtime response wrappers.
- Removed the daemon port environment override in favor of the fixed daemon port behavior.

### Adapters

- Added quote and bookmark counts to Twitter timeline output.
- Hardened the Twitter tweet deletion flow.

## [0.2.0](https://github.com/agentrhq/webcmd/compare/webcmd-v0.1.2...webcmd-v0.2.0) (2026-07-03)

### Highlights

- Added the release-note helper library and Gemini-backed release-note generation flow.
- Ported upstream transport deadline handling into the Cloak runtime.
- Moved the repository toward English-first docs, skills, and release materials.

### Improvements

- Added reusable release-note helper utilities.
- Added Gemini release-note generation with workflow fallback behavior.
- Scaffolded Mintlify docs and release documentation.
- Rewrote the README for the Webcmd project direction.
- Added repository security documentation.

### Fixes

- Scoped release-note failures so release-please notes remain intact when enhanced generation cannot run.
- Addressed release-note review findings.
- Ported upstream transport deadlines to the Cloak runtime.
- Preserved skill guidance during translation.
- Synced the npm lockfile peer dependency.
- Removed stale deleted-adapter references from docs and tests.

### Adapters

- Cleaned up the adapter catalog by removing Chinese-first built-in adapters.
- Removed references and tests for adapters that had already been deleted.

## [0.1.2](https://github.com/agentrhq/webcmd/compare/webcmd-v0.1.1...webcmd-v0.1.2) (2026-07-03)

### Highlights

- Focused patch release for making the npm package install and execute correctly.

### Improvements

- Relaxed the doctor runtime version warning so compatible runtimes are not reported too aggressively.

### Fixes

- Included the executable in the npm package.
- Parsed `npm pack` JSON correctly even when lifecycle output is present.
- Relaxed the doctor runtime version warning.

## [0.1.1](https://github.com/agentrhq/webcmd/compare/webcmd-v0.1.0...webcmd-v0.1.1) (2026-07-03)

### Highlights

- Published the next installable npm version after the initial package release.

### Fixes

- Released the next publishable npm version.

## 0.1.0 (2026-07-03)

### Highlights

- Initial Webcmd release.
- Introduced a TypeScript/JavaScript toolkit for turning websites, browser sessions, desktop apps, APIs, and local tools into deterministic CLI commands.

### Improvements

- Established the core CLI runtime.
- Added the command registry and manifest foundation.
- Introduced the adapter/plugin architecture and authoring workflow.
- Added the Cloak-backed browser automation layer for inspecting pages, executing browser actions, capturing context, and exposing stable command surfaces.

### Adapters

- Introduced the adapter foundation for building repeatable command surfaces over target sites, apps, APIs, and tools.
