# binary-heap-plus-rs

![Rust](https://github.com/sekineh/binary-heap-plus-rs/workflows/Rust/badge.svg)

Enhancement over Rust's `std::collections::BinaryHeap`.

It supports the following heaps and still maintains backward compatibility.
- Max heap
  - Use `BinaryHeap::new()` or `::with_capacity()`
- Min heap
  - Use `BinaryHeap::new_min()` or `::with_capacity_min()`
- Heap ordered by closure
  - Use `BinaryHeap::new_by()` or `::with_capacity_by()`
- Heap ordered by key generated by closure
  - Use `BinaryHeap::new_by_key()` or `::with_capacity_by_key()`

Other notable added methods are:
- `BinaryHeap::from_vec_cmp()` and `BinaryHeap::from_vec()` for more generic construction.
- `.into_iter_sorted()` which is less-surprising version of `.into_iter()`. The implementation is backported from `std`.
- `.replace_cmp()` which replace the comparator of the existing heap.

## MSRV (Minimum Supported Rust Version)

This crate requires Rust 1.36.0 or later.

# Changes

See CHANGELOG.md.
https://github.com/sekineh/binary-heap-plus-rs/blob/master/CHANGELOG.md

# Thanks

- I received many valuable feedback from Pre-RFC thread [1].
  - The current design is based on @ExpHP's suggestion that compiles on stable compiler.
  - DDOtten, steven099, CAD97, ExpHP, scottmcm, Nemo157 and gnzlbg, thanks for looking into the design!
- @ulysseB sent me a first pull request!
- @inesseq contributed feature `serde1`.
- @davidli2010 contributed comparator update and `unsafe` perf optimazation.

# References

See the following discussions for the background of the crate:
- [1] https://internals.rust-lang.org/t/pre-rfc-binaryheap-flexibility/7482
- https://users.rust-lang.org/t/binaryheap-flexibility-revisited-supporting-other-than-max-heap/17062
- https://users.rust-lang.org/t/binaryheap-flexibility/8766
- https://github.com/rust-lang/rust/issues/38886
