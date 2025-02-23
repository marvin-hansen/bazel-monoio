# Readme

Replication of multiple build issues in Bazel with the [monoio crate](https://github.com/bytedance/monoio/tree/master/monoio).

## Summary

The  [monoio crate](https://github.com/bytedance/monoio/tree/master/monoio) cause multiple build issues with Bazel.

* Cross compilation with llvm/clang fails
* Cross compilation with musl fails
* Vendoring fails

## Cross compilation with llvm/clang

This fails with an apparent linker error ld.lld: error: undefined symbol: statx

* Error log: [cross_llvm_error_log.txt](cross_llvm/cross_llvm_error_log.txt)
* Replication: [cross_llvm](cross_llvm/README.md)

## Cross compilation with musl fails

This fails with a similar error 

``6 | use libc::statx;
|     ^^^^^^^^^^^ no `statx` in the root``

* Error log: [cross_llvm_error_log.txt](cross_musl/cross_musl_error_log.txt)
* Replication: [cross_musl](cross_musl/README.md)


## Vendoring fails

The Vendoring failure seems to be caused by auto-const-array.
The exact reasons seems unknown.

* Error log: [vendor_error_log.txt](vendor/vendor_error_log.txt)
* Replication: [vendor](vendor/README.md)