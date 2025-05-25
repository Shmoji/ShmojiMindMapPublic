  * tracking my thoughts ^5p9Bk0ezi
    * [[2023-10-19]]
      * if there's gonna be a project that leads to AI agents that can be prompted with simple prompt but complex task like "create the frontend of a twitter clone using next.js and tailwindcss. Populate it with dummy data" - i predict it's going to be Morph Labs, Lean, and Rift that give possibly the critical piece that leads to this.
      * Although, it may also be Wolfram's tech that leads to it - i find it harder to understand though, so im uncertain.
        * me: How is what Morph is doing with Lean different from what Wolfram's tech does? I get the sense they are both meant for proving "things" - but i guess just meant for proving different things? (also, im not super knowledgeable on Wolfram tech)
          * GPT4:
            * Foundation:
              * Morph: Utilizes Lean, a theorem prover and programming language aimed at formal verification, which is the practice of proving that systems have certain properties in a mathematically rigorous way.
              * Wolfram: Based on symbolic computation which manipulates mathematical expressions and other data symbolically, enabling it to work on problems in a way that is somewhat akin to the symbolic manipulations performed by humans.
              * me: can you expand on the differences in the foundation you gave?
                * Formal Verification and Theorem Proving (Morph/Lean):
                  * Logic-Based: Lean operates on a formal logical foundation, enabling precise definition and verification of mathematical theorems or software correctness.
                  * Verification: It's a tool for ensuring that certain properties hold within a defined system, which is critical in fields like aerospace, healthcare, or any area where system failure could have dire consequences.
                  * Explicit Proof Construction: Lean requires users to construct proofs explicitly, although it has automation to assist in this process. This meticulous approach ensures the validity of the proof.
                * Symbolic Computation (Wolfram Technology):
                  * Symbol Manipulation: Wolfram operates on symbolic computation, where mathematical expressions are manipulated in a form that remains symbolic, rather than numeric.
                  * General Computation: It’s more of a general-purpose computational tool that can handle a vast array of mathematical and algorithmic tasks beyond theorem proving.
                  * Automated Reasoning: Wolfram can automate a lot of reasoning tasks and can solve equations, simplify expressions, or prove certain types of theorems without the user needing to provide explicit step-by-step proofs.
                * Type System:
                  * Lean: Has a strong type system which is fundamental for its verification capabilities. This type system ensures that only statements that adhere to strict logical and type-correctness criteria are accepted.
                  * Wolfram: Doesn't have a type system in the same rigorous sense as Lean. Its symbolic nature allows for more flexible manipulation of expressions.
                * Language:
                  * Lean: The language used for expressing theorems and proofs is based on dependent type theory, which is a formal framework used in logic and computer science.
                  * Wolfram: Utilizes its own language, Wolfram Language, which is designed for symbolic computation and has natural language processing capabilities.
                * Understanding these foundational differences could potentially guide how you approach problems requiring rigorous proof versus those needing a broader computational scope. For instance, in your pursuit of creating a marketplace of desires or an app mapping desires to optimal UX flow, the computational breadth of Wolfram might be more suited, whereas for formalizing a novel mathematical concept as part of your innovative explorations, Lean's rigorous formal verification could be invaluable.
            * Purpose:
              * Morph: Its core is in formal verification and theorem proving, making it suitable for applications where absolute rigor is necessary such as in verifying the correctness of critical software or proving mathematical theorems.
              * Wolfram: More of a computational software that is used in a variety of scientific, engineering, mathematical, and computing fields. Its theorem proving capabilities are part of a broader suite of functionalities.
            * User Interaction:
              * Morph: Its user interaction is more akin to traditional programming or mathematical logic, requiring the user to have a solid understanding of formal logic and proof techniques.
              * Wolfram: Offers a more intuitive and visually engaging experience, leveraging its natural language understanding capabilities to interpret and execute user inputs.
            * Community and Ecosystem:
              * Morph: Lean has an open-source community which contributes to its libraries and helps in evolving the system.
              * Wolfram: It's a more commercial and closed-source ecosystem, with a long history and a wide range of built-in capabilities.
            * Capability:
              * Morph: Ideal for tasks requiring rigorous proof, like formalizing mathematics or verifying critical systems.
              * Wolfram: Geared towards computational tasks across various domains, with capabilities ranging from symbolic algebra, calculus, to data analysis, and visualization.
            * Integration with Other Technologies:
              * Morph: Being open-source, it has the potential for integration with other systems although it might require more effort.
              * Wolfram: Has built-in integrations and a broader range of import/export options given its mature ecosystem.

  * key points
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/autoformalization#^r-3-8rms7|Morph Labs is working on autoformalization in relation to chatbots]]
    * they built [[Lean]] - a functional language or something like that
    * they fine-tuned their own LLM for Lean
    * they built Rift vsCode extension that uses AI agents to help you code entire apps, write unit tests, ask questions, etc
  * products, solutions
    * [[Rift vsCode extension]]
    * [[Lean]]
    * Moogle
      * Moogle is a semantic search engine for mathlib. It lets you find theorems using natural language, and was built with some of the same techniques we used to create Morph Prover v0 7B. We hope this makes it easier for people with math knowledge but not mathlib knowledge to navigate mathlib.
      * Moogle has a VS Code extension