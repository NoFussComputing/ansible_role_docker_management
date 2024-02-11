## 0.2.0 (2024-02-11)

### Bug Fixes

- **docker_containers**: [58f88721](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/58f88721cc719ce80eb1dc33a8b37c7c92b4a4b1) - dont log or provide dif due to secrets [ [!20](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/20) ]
- **install**: [2b5ce0a7](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/2b5ce0a7caceb37b3d790a85f7d3dd09b1843804) - use correct vars so ubuntu works [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **install**: [6628dd93](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/6628dd93efb5055feef2ff776258668f3fa156a2) - ensure docker repo and signing key available [ [!10](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/10) [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **containers**: [5849ea32](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/5849ea32a7c4e5f3d9028dbbb44b70f93a5839f1) - typo in log_driver var [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **containers**: [5eba9aeb](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/5eba9aebfde283dff6a3413a4f7d2bdaf727a3cd) - sytax error environment -> env [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **containers**: [48efb029](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/48efb0296c247630357c28e4a9b0cef69f8dc97e) - if no comparisons specified, enforce strict ALL [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **containers**: [0946be67](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/0946be67eeb20c2a8b6f599e171dec9af01796ad) - syntax error ports -> exposed_ports [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **volume**: [aadcf115](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/aadcf115cac0b007242aea21e1ec31e39d7206c3) - correct typo of default as present [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]

### Code Refactor

- [e4a6465d](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/e4a6465ded481f409ab347418e94525e9b44b2cd) - task file cleanup [ [#3](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/3) ]

### Features

- **networks**: [b5e17e30](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/b5e17e30319fc51c9b7420969059b044f2324fad) - added option for internal networks [ [#3](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/3) ]
- **container**: [630f85e7](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/630f85e7dd8821e4c66af8afbab38a6420512720) - enforce strict comparisons by default [ [#3](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/3) ]
- **install**: [ddcf1e86](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/ddcf1e866566df0049aa69886fcc61fa1a2dee5f) - only run install tasks once [ [#3](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/3) ]
- **repo_key**: [abd19c16](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/abd19c164322ef4c83937ee01885211dae840fda) - set file perms [ [#3](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/3) ]
- **containers**: [67622b30](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/67622b307b0bb14cfa378640fdb44c9a55cb4c47) - added option to output 'diff' [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **containers**: [795c6d04](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/795c6d04d0f10176169062865387c0040642f622) - added option 'tty' [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- [a7c42294](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/a7c422941eec9464b130731de9b5bfdbd1387862) - dont use ansible tags [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **containers**: [bbb0659e](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/bbb0659e5f2c4c7f420c5fa6fcbc218bbea4d01c) - if specified set hostname and domain name [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **install**: [b609b69b](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/b609b69beb2131106eb7bb518d62fa6f8c9a1390) - ensure service enabled and started [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **install**: [82a23bda](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/82a23bda6f4f5f1f194d1f94fd701461b305dce9) - update package cache [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **install**: [d56fbbca](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/d56fbbcaf12bafcb774b40346c30de6a7ece97c1) - ensure package cache is updated before install [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **images**: [ef7c3a11](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/ef7c3a112567b3e19627732ed5f4d5588b442345) - default set to pull [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **containers**: [9a1cddea](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/9a1cddea51844f62f74e10bbcf597f0cdf308e79) - default set to started [ [#2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/2) ]
- **automation**: [06343f69](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/06343f69eab5138e48eec9d6b4c49418834af3b3) - add nfc automation file [ [!5](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/5) ]

## 0.2.0rc0 (2023-06-15)

### Bug Fixes

- **tasks**: [f5c3e9b2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/f5c3e9b246ce38ffb80f91346a7f3f3ce164d96b) - loop vars are lists, expand [ [!4](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/4) ]
- **tasks**: [f1d498bf](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/f1d498bf967e8736047c6d40383b46af20353be4) - if keyword not specified omit [ [!4](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/4) ]
- **tasks**: [9eedb7c2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/9eedb7c29a62ff1014ff6ddfcd7ddb7ae3b8dae5) - added required main.yml [ [!4](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/4) ]
- **handler**: [906e81e5](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/906e81e5d955ff2dd2f32ca274de47a2cb06d69f) - use correct ansible module [ [!4](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/4) ]

### Code Refactor

- [cfed1f19](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/cfed1f19ccbb687bc8a4fddb4496e19ea4250683) - remove error code [ [!4](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/4) ]

### Documentaton / Guides

- **meta**: [c7b56ac2](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/c7b56ac2d3a58c9516375e97102fb4f5d18d51d1) - updated galaxy info [ [!4](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/4) ]

### Features

- **docker_containers**: [91cb97d9](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/91cb97d9970ebee50dc93edc9480a6315410d245) - support setting published_ports [ [!4](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/4) ]

## 0.1.0 (2023-06-12)

### Bug Fixes

- [474b0a91](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/474b0a91f2c6c5768bdd859e67620ec063f7d166) - current version corrected [ [!3](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/3) ]

### Code Refactor

- **docs**: [936d0a2c](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/936d0a2ca427569cfae57b041100ca9bb72d93bd) - correct linting errors [ [!1](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/1) [#1](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/1) ]

### Features

- **docs**: [52f60459](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/52f604594f743f176b23dbbb4c16bfbeb5c6c6ec) - initial adding of the documentation [ [!1](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/1) [#1](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/1) ]
- **ci**: [6a10485e](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/commit/6a10485e9d5550b14f3e7b4bf2c9b0b377a793d1) - added gitlab-ci project [ [!1](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/merge_requests/1) [#1](https://gitlab.com/nofusscomputing/projects/ansible/docker_management/-/issues/1) ]

## 0.0.1 (2023-06-12)
