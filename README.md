## Introduction
   The Clang Compiler is an open-source compiler for the C family of programming languages, aiming to be the best in class implementation of these languages. Clang builds on the LLVM optimizer and code generator, allowing it to provide high-quality optimization and code generation support for many targets. For more general information, please see the Clang Web Site or the LLVM Web Site.

   This document describes important notes about using Clang as a compiler for an end-user, documenting the supported features, command line options, etc. If you are interested in using Clang to build a tool that processes code, please see “Clang” CFE Internals Manual. If you are interested in the Clang Static Analyzer, please see its web page.

   Clang is one component in a complete toolchain for C family languages. A separate document describes the other pieces necessary to assemble a complete toolchain.

   Clang is designed to support the C family of programming languages, which includes C, Objective-C, C++, and Objective-C++ as well as many dialects of those. For language-specific information, please see the corresponding language specific section:

C Language: K&R C, ANSI C89, ISO C90, ISO C94 (C89+AMD1), ISO C99 (+TC1, TC2, TC3).
Objective-C Language: ObjC 1, ObjC 2, ObjC 2.1, plus variants depending on base language.
C++ Language
Objective C++ Language
OpenCL C Language: v1.0, v1.1, v1.2, v2.0.

   In addition to these base languages and their dialects, Clang supports a broad variety of language extensions, which are documented in the corresponding language section. These extensions are provided to be compatible with the GCC, Microsoft, and other popular compilers as well as to improve functionality through Clang-specific features. The Clang driver and language features are intentionally designed to be as compatible with the GNU GCC compiler as reasonably possible, easing migration from GCC to Clang. In most cases, code “just works”. Clang also provides an alternative driver, clang-cl, that is designed to be compatible with the Visual C++ compiler, cl.exe.

In addition to language specific features, Clang has a variety of features that depend on what CPU architecture or operating system is being compiled for. Please see the Target-Specific Features and Limitations section for more details.

The rest of the introduction introduces some basic compiler terminology that is used throughout this manual and contains a basic introduction to using Clang as a command line compiler.
