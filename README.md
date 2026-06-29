# Cripton

<p align="center">

![Web3](https://img.shields.io/badge/Web3-Blockchain-F16822?logo=web3.js&logoColor=white&style=flat-square)
![Solana](https://img.shields.io/badge/Solana-14F195?logo=solana&logoColor=&style=flat-square)
![Angular 19](https://img.shields.io/badge/Angular-19-DD0031?logo=angular&logoColor=white&style=flat-square)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?logo=nestjs&logoColor=white&style=flat-square)
![WebGPU](https://img.shields.io/badge/WebGPU-005A9C?style=flat-square)
![IPFS](https://img.shields.io/badge/IPFS-65C2CB?logo=ipfs&logoColor=white&style=flat-square)
![PostgreSQL 18](https://img.shields.io/badge/PostgreSQL-18-4169E1?logo=postgresql&logoColor=white&style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white&style=flat-square)

</p>

## Demo

The app is up and running at https://cripton.app 💻

## Philosophy


## Project Structure & Technologies Used

Cripton is split into 5 git repositories, and a nice way to understand the structure is to look at this mind map:

```mermaid
mindmap
  root((Cripton))
    Frontend — Angular + PrimeNG
      Solana Blockchain
      solana-vanity-gpu
        WebGPU-Ed25519-Scalar-Multiplication
          WebGPU-SHA512
          WebGPU-Base58
    Backend — NestJS
      Solana Blockchain
      Database — PostgreSQL
      IPFS Storage
        Pinata
        Filebase
```

As most other web-based applications, Cripton is generally split into backend and frontend that communicate with each other via REST API. Backend is built on NestJS — a progressive Node.js framework, and frontend — on Angular. Because the app is built around the Solana blockchain, external libraries like `@solana/web3.js`, `@metaplex-foundation/umi`, and `@solana/wallet-adapter` are heavily used for building transactions, communicating with user wallets, and generally interacting with Solana on both frontend and backend.

More details on the stack used:
- Frontend uses [PrimeNG](https://v19.primeng.org/) components & styles library for UI. In the mindmap you can also see libraries `solana-vanity-gpu`, `WebGPU-Ed25519-Scalar-Multiplication`, `WebGPU-SHA512`, and `WebGPU-Base58`, which were all customly created for Cripton with one goal in mind: <b>perform [vanity keypair](https://www.reddit.com/r/BitcoinBeginners/comments/7y8i6k/what_is_a_vanity_key/) search on the GPU directly in the browser</b>. For this task Cripton uses <b>WebGPU</b> — a relatively new JavaScript API for general-purpose GPU computing. More on that in the Features section.
- Backend follows a pretty common Nest app architecture. It uses [PostgreSQL](https://www.postgresql.org/) as its database, which is mainly needed to just store service prices, referral links information, and links to images and token metadata files in the [IPFS storage](https://ipfs.tech/). IPFS is a decentralized file system where all the user-uploaded content like token metadata and images actually lives. Cripton supports [Pinata](https://pinata.cloud/) and [Filebase](https://filebase.com/) as [IPFS pinning services](https://pinata.cloud/blog/what-is-an-ipfs-pinning-service/), currently Filebase is used in production.
- In production, all components of the app (frontend, backend, database) are running as [Docker](https://www.docker.com/) containers. In development only the database is dockerized, and frontend and backend run as normal Node.js processes.

Links to git repositories:
- [Frontend](https://github.com/Dcfgvy/cripton-frontend)
- [Backend](https://github.com/Dcfgvy/cripton-backend)
- [WebGPU-Ed25519-Scalar-Multiplication](https://github.com/Dcfgvy/WebGPU-Ed25519-Scalar-Multiplication)
- [WebGPU-SHA512](https://github.com/Dcfgvy/WebGPU-SHA512)
- [WebGPU-Base58](https://github.com/Dcfgvy/WebGPU-Base58)

## Features

### Vanity keypair search on the GPU
 `WebGPU-SHA512` and `WebGPU-Base58` contain [WGSL](https://www.w3.org/TR/WGSL/) ...

## Run Locally


## (Not) Running Tests

There are no unit or end-to-end tests implemented yet. But a contribution would be extremely valuable.

## Development pipeline, CI/CD

## Roadmap

## Contributing

## Licenses

Frontend & backend are under GNU General Public License v3.

`WebGPU-Ed25519-Scalar-Multiplication`, `WebGPU-SHA512`, and `WebGPU-Base58` are under MIT License.

This documentation is under GNU Free Documentation License.

[![GNU GPL v3](https://www.gnu.org/graphics/gplv3-or-later.png)](https://www.gnu.org/licenses/gpl-3.0)<br>
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![License: GFDL 1.3](https://img.shields.io/badge/License-GFDL%201.3-blue.svg?style=flat-square)](https://www.gnu.org/licenses/fdl-1.3.html)

## Authors

- [@Dcfgvy](https://www.github.com/Dcfgvy)


![Logo](https://cripton.app/images/logo.png)
