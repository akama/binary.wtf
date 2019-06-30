---
title: Returning Records Efficiently in OCaml
date: '2019-06-30T12:39:15-05:00'
tags:
  - OCaml
---
One of my coworkers recently taught me this great syntactic trick for saving records in OCaml. Frequently I have a record with 4-6 fields that is managing the state of a process or request and I want to write a function to update only one of those fields. Let's assuming the following is our record.
```
type test_record = {
  field1 : int;
  field2 : string;
  field3 : int option;
  field4 : string list;
}
```
Now we want to update an instance of this to set `field1` to 3. Here is the quick way to update a single field.
```
let update_one_thing (r : test_record) =
  let field1 = do_something_here r.field1 in
  { r with field1 }
```
I find this much easier to read and write than the other method. I don't know why I don't see this in more code so hopefully more people start to use it.
