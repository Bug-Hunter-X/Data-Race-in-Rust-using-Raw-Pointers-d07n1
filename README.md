# Data Race in Rust using Raw Pointers

This repository demonstrates a potential data race in Rust that can occur when using raw pointers without proper synchronization mechanisms.  The `bug.rs` file contains the buggy code, while `bugSolution.rs` provides a safe and corrected version.

## Bug Description
The primary issue stems from directly manipulating vector elements via a raw pointer (`as_mut_ptr()`). If this code were part of a multi-threaded application, concurrent access to the vector by other threads would lead to unpredictable behavior—a data race.

## Solution
The solution avoids unsafe code and leverages Rust's ownership and borrowing system to prevent data races.  This eliminates the risk of concurrent modification.