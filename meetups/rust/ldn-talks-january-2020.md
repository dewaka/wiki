# LDN Talks January 2020

## Chris Whealy on Pororus_Absorber

- Speaker - [Chris Whealy](http://whealy.com/) https://twitter.com/LogaRhythm
  - He is a drummer and home practice is what motivated him to build an acoustic environment
- Project - [Pororus_Absorber](https://github.com/ChrisWhealy/porous_absorber)
  - App is designed to assist acousticians when designing environments such as home cinemas 
  - It calculates the acoustic absorption curve of a variety of absorption devices mounted against a rigid backing such as a brick wall
  - This is a Rust-WASM project which is a port of an Excel sheet he wrote about 15 years ago using VBScript!
- This was his first Rust WASM project and due to that it took about three months for this project.
- Maths for acoustic calculations were not new to him and they were basically ports from Excel to Rust.
- If done again, he mentioned that he would be able to do the project in a couple of weeks now.
- Some design decisions, such as using JavaScript for event handling could be revisited if reimplemented from scratch.
  - Since WASM allows capturing the DOM at the start, even handling _can_ be done completely within Rust-WASM.
  - For some functions he is passing simply `JSObjects`, which can stand for _anything_ - this is something he found that he preferred from experience given that obscure error messages one gets if type conversions fail w.r.t. more specific parameters.
  
## Andrius Aucinas on Brave adblock improvements with Rust

- [Andrius Aucinas](https://uk.linkedin.com/in/andriusaucinas) is a performance researcher at Brave and was previously the Head of Engineering at HAT (Hub of All Things), which he co-founded.
- Andrius' Twitter - https://twitter.com/AndriusAuc
- Project - https://github.com/brave/adblock-rust
- He is part of the team responsible for porting Brave Browser's AdBlock engine over from C++ to Rust, he'll be sharing some insights and experiences of that development process.