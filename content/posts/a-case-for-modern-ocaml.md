---
title: A Case for Modern OCaml
date: '2021-02-18T09:52:01-06:00'
categories:
  - ''
tags:
  - ocaml programming
keywords:
  - ocaml programming
---
A topic that is often discussed when programmers get together is about programming language choice and the perceieved benefits of said language. In recent memory, I've heard people discuss picking Go for static binaries, Rust for memory safety, or using new Python to get it's types. It's often an immensely complicated choice with many factors influencing it but I'd like to layout some of the reasons that I think there is a compelling case for modern OCaml and why you might want to use it for your next project.

Most people who have had a academic computer science education have enountered OCaml before in a limited context. Often it's used to teach typed languages, compilers, or any other varity of CS concepts. Unfortunately this is often taught using an OCaml compiler and toolchain that is quite old and for lack of a better term, crusty. However the modern OCaml toolchain has seen a significant amount of work in recent years and is now on par or superior than most other language ecosystems. I'd encourage individuals to look past their previous experience and give the modern language a second pass. 

The stars of the current OCaml tooling world are opam & dune. Opam is the language package manager. Besides the obvious feature of downloading/installing and managing packages, opam has the handy feature that it also manages compilers as well. This includes the ability to make a seperate environment in any folder making it trivially easy to keep multiple projects with seperate dependancies organized easily. It also includes the ability to symlink local installs which makes it easy to share the same install between different code branches on the same machine.  Opam also includes support for locking dependancies to exact versions, making it easy to ensure that different installs of a project produce the exact same result. It also has support for pinning which allows you to override the install location of an upstream dependency in a single command which can be very handy for using a fork with a specific patch or bugfix. 

Dune the build system for OCaml/Reason (a sister language of OCaml) is the other side of the OCaml tooling system. Dune allows you to write very simple s-expressions in a file and get consistent tooling for building/running that works well out of the box. One of the features that really shines in dune is the ability to have multiple executables and/or libraries all inside the same dune workspace (read: top level file folder). This means that inside that folder, you can move/rearrange where those compents are and dune will do all the hard work of linking them together and producing a build without making any changes to the dune file. This ability makes it very easy to manage large codebases in a single repo. In addition, it makes it easy to have internal libraries that are linked against a wide varity of other libraries or services. Dune allows for significant complexity, such as managing the process of linking against c libraries, as to be expected of a build tool but Dune is exceedingly well designed to only expose that complexity when needed.

OCaml is a strongly typed language with support for product, sum types as an example. This often carries significant connotations but it is one of the strongest points of the language. One aspect of computer systems that is often fraught with difficulty is the interfaces between different pieces of the codebase. A good type system and design will help you mitigate some of that difficulty by allowing the computer to check some aspects and alert if something is incorrect. Rather than viewing this ability as a draconian restriction of freedom, this ability is in fact freeing the program author from significant mental fatigue. The ability to designate some level of checking to a compiler allows the author to focus on the high level logic of what is happening rather than worry about data validate/interface concerns. 

This type system and it's associated assistance really starts to shiny in the maintaince of large code bases. Refactoring has traditionally been one of the most tedious, monotonous tasks, and failure prone tasks.  However a type system has two significant ability within the context of refactoring. The first is is the joy of changing a function signature/type and allowing the compiler to find all locations that are broken. Rather than relying on search tools that have a superficial level of understanding of the language, allowing the language itself guide us to sections of code that need to be changed is much more reliable. The second aspect is the ability to have confidence in the output after a refactor given a well designed typed application. Because the compiler can check on the interfaces between sections of the codebase, the author can have confidence in the refactored codebase as a whole. 

Often large sets of tests are used to enable developers to have confidence in their refactoring.





covering 

\> dune/opam

\> types

\---

\> gc/security

\> dev env

\> readability

\> libraries

bonus libraries

\> mirage

\> owl

\> bap

\> menhir
