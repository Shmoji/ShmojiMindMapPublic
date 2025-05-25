
  * questions
    * when you run command like "cargo test --target wasm32-unknown-unknown" - what is the target?
      * GPT4: "target" refers to a "compilation target." This is a specification for the platform you are compiling your code for. In the world of Rust programming, the target determines the architecture, operating system, and sometimes the environment for which the code is being compiled.
        * Here, wasm32-unknown-unknown is a target triple, a standard format in systems programming for describing a platform. It consists of three parts:
        * Architecture: wasm32 indicates that the target architecture is WebAssembly (WASM), a binary instruction format for a stack-based virtual machine, designed for efficient execution and compact representation. This is used to run code on the web at near-native speed.
        * Vendor: unknown in this context means that there is no specific vendor.
        * Operating System: The second unknown implies that there is no specific operating system being targeted. This makes sense for WebAssembly, which is designed to be platform-agnostic and run in a variety of environments, including web browsers.
      * GPT4: So, in summary, the --target wasm32-unknown-unknown part of your command tells Cargo to compile the Rust code for the WebAssembly platform, without targeting a specific vendor or operating system. This is typically used when you want to compile Rust code that can run on the web.
      * me: so i i ran that previous command and then also ran "cargo test" - are they running the same tests just on different architectures?
        * GPT4: yes. but they are being compiled for and run on different architectures. cargo test will run test for default target, which is typically the architecture of the machine you're running the command on.
  * related
    * [[compiling and building]]
