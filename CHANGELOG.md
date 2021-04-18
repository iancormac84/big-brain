<a name="0.3.2"></a>
## 0.3.2 (2021-04-17)

This is a quick bugfix. Shoutout to [@ndarilek](https://github.com/ndarilek)
for finding this one and giving me a chance to debug it!

tl;dr: Bevy's hierarchy system *requires* that all children have `Transform`
and `GlobalTransform` also attached, otherwise it just... kills them.

#### Bug Fixes

* **scorer:**  stop attaching duplicate scorers ([10a6d022](https://github.com/zkat/big-brain/commit/10a6d022ec682e33b98309318020c9068be4cea2))
* **thinker:**  add Transform and GlobalTransform ([ed3a7cb3](https://github.com/zkat/big-brain/commit/ed3a7cb3c03e27b76b374f75ac179f29c979e4cf))

<a name="0.3.1"></a>
## 0.3.1 (2021-04-14)

Just a quick release because I broke docs.rs :)

#### Bug Fixes

* **build:**  remove .cargo/config.toml to make docs.rs happy ([393d9807](https://github.com/zkat/big-brain/commit/393d9807576d21c7234667b1f9914f1886579bd0))


<a name="0.3.0"></a>
## 0.3.0 (2021-04-14)

This is a major overhaul of the Bevy API. It removes `.ron` support
altogether, in favor of plain old Rust builders.

#### Breaking Changes

* The `.ron` Thinker definition API is gone. Use the ThinkerBuilder API instead.
* The `Action` and `Scorer` derive macros are gone, including all of `big_brain_derive`.
* Measures and Weights are gone.
* `big-brain` no longer exports everything from the toplevel. Use `big_brain::prelude::*` instead.

#### Bug Fixes

Probably.

#### Features

* New builder-based Thinker API!
* Composite Scorers: `FixedScore`, `AllOrNothing`, and `SumOfScorers`.
* Composite Action: `Steps`, for sequential Action execution.