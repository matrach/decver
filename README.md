
# Decimal Versioning Specification – a system for end-user humans

## Rationale

Have you ever read aloud Python 2.5 as **"two and a half"**? I did. My grandma would read it like this as well. Why would you expect a typical end user (in 2+ billion world) to read is as "two dot five"?

We can clearly see major end-user applications steering away from semver. Chrome and Firefox, for instance, currently use single-number versioning and already reached ver 100+. What does "breaking change" even mean for end-user applications? Some developers don't like huge numbers after a dot (looking at you, Linux), and increment the major version arbitrarily. 

15 years ago I have seen some instances of decver and laughed at it, but now I think: why not...

### Example

Consider an online game updated quarterly. The previous releases were ``6.7``, ``6.8``, ``6.9``. What version number comes next?

~~6.10~~... Of course **7.0** it is! Cannot you spot a simple arithmetic sequence? Even little children know that 6.10 < 6.9. (And some wonder why the trailing zero).

## Short spec

The main assumption of *decver* is that when  ~~normal~~ people see numbers, they assume decimal. The core rule states that:

**verA** is "newer" than **verB** <=> ``float(verA_string) > float(verB_string)``

The rest is to be decided individually in each case.

### Suggested interpretation

1. Plan major milestone releases as most yearly or bi-yearly. That will increase the major version (number before the dot).
1. Release at most 9 main *preview* versions, where the decimal part represents feature progress towards the milestone.
1. Any minor fix releases only slightly take the system towards the goal, therefore only slightly increase the number. E.g. `4.7` -> `4.71`.
1. Version release candidates with a sequence approaching the next integer. E.g. `4.9` -> `4.95` (aka alpha) -> `4.99` (aka beta) -> `4.999` (aka rc-1). Finally release version `4.(9)` == `5.0`.

## Full specification
TONDO

## Who uses decver?

* [TeX](https://texfaq.org/FAQ-TeXfuture)
* [Tib](https://tibia.fandom.com/wiki/Major_Updates)[ia](https://tibia.fandom.com/wiki/Version_7_Updates)

## FAQ

### Is this a joke?

Kinda...

### Any other thoughts?

Just use YYYY.MM versioning system...