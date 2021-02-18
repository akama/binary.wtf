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





covering 

\> dune/opam

\> types

\> gc/security

\> dev env

\> libraries



bonus libraries

\> mirage

\> owl

\> bap

\> menhir
