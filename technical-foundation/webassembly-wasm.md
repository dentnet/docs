# WebAssembly (Wasm)

WebAssembly is used in Substrate-based blockchains like DENTNet and Polkadot as the compilation target for the runtime.&#x20;

Simplified, this means the runtime for a blockchain node on DENTNet is independent of the computer architecture and could run on any browser. Still, DENTNet provides an executable for Linux machines, that starts the actual wasm-based runtime.

This separation allows DENTNet to update the blockchain logic without the explicit need to update all executables on nodes and validators. In the beginning, updates of the executable might happen e.g. to improve the wasm interpreter.

Webassembly is an industry standard. Further information about Webassembly can be found at [https://webassembly.org/](https://webassembly.org/).



### &#x20;<a href="#resources" id="resources"></a>
