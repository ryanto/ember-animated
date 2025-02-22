# master

# 0.6.1
 - BUGFIX: polyfill Element.remove on IE11
 - BUGFIX: subpixel rounding could cause text wrapping during animation of inline elements

# 0.6.0
 - BUGFIX: we sometimes threw a "function expected" Exception on Microsoft Edge when using <AnimatedOrphans />
 - DOCS: @jenweber fixed a broken link
 - BUGFIX: there was a race condition if any animator component received two changes before the first could even begin running the user's transition
 - HOUSEKEEPING: issue template added by @samselikof
 - HOUSEKEEPING: deleted unnecessary package-lock.json by @Turbo87
 - DOCS: refer to yarn instead of NPM in the CONTRIBUTING docs, by @outdoorsy
 - HOUSEKEEPING: upgrade to Ember 3.10 and fix deprecations, by @cibernox
 - DOCS: improved use of `htmlSafe` in examples to demonstrate safer patterns
 - ENHANCEMENT: added easing option support to the scale motion, by @nibynic

# 0.5.4
 - HOUSEKEEPING: switch to released version of ember-angle-bracket-invocation-polyfill, by @danwenzel

# 0.5.3

 - HOUSEKEEPING: configure travis releases by @samselikoff

# 0.5.2

 - DOCS: major docs improvements by @samselikoff

# 0.5.1
 - COMPATABILITY: update for compatibility with internal change to Ember 3.10 decorators, by @geoffreyd.

# 0.5.0
 - BREAKING CHANGE: changes the default duration from 2000 to 500
 - DEPRECATION: AnimatedContainer's "class" _argument_ is deprecated in favor of the class _attribute_. The old usage was

    ```hbs
    {{!-- these are exactly equivalent to each other --}}
    {{#animated-container class=something}}
    <AnimatedContainer @class={{something}}>
    ```

    The new usage is

    ```hbs
    <AnimatedContainer class={{something}}>
    ```

# 0.4.1
 - BUGFIX: previous style continuity feature was slightly too aggressive for line-height
 - BUGFIX: fix a crash when using SVGs as orphan sprites

# 0.4.0
 - ENHANCEMENT: improved style continuity for orphan sprites
 - DOCS: improved styling by @samselikoff

# 0.3.2
 - HOUSEKEEPING: compatibility with newer ember versions with help from @toovy and @cibernox
 - DOCS: sprite docs improvements by @samselikoff

# 0.3.1
 - ENHANCEMENT: new beacon API
 - DOCS: lots of new docs added, thanks @savvymas

# 0.3.0

 - ENHANCEMENT: now completely jQuery-free. Thanks to @cibernox and @mikoscz.
 - ENHANCEMENT: `animated-each` now yields an `index` variable, just like regular Ember `each`. Thanks @Cryrivers.
 - ENHANCEMENT: much progress on integrating ember-cli-addon-docs and beginning to document methods. Thankss @Oreoz, @Turbo87, @chrism. Deployed docs site coming very soon.

# 0.2.0

 - BREAKING: Sprite no longer has initialOpacity and finalOpacity. These are now covered by initialComputedStyle and finalComputedStyle, which are also extensible to track many other CSS properties.

 - BREAKING: orphaned transitions will no longer see removedSprites by default when the corresponding animator is being destroyed. It's usually not what you want. You can opt-in to animating removed sprites by setting finalRemoval=true on the animator (this is analogous to initialInsertion). None of this impacts an animator's ability to match against other animators, even when it's being destroyed (sentSprites are still always available).

# 0.1.0

 - BREAKING: removed waitForAnimations in favor of animationsSettled. It works better with new style async Ember tests.
 - BREAKING: transitions now received the TransitionContext as an argument instead of as `this`.
 - BREAKING: the TransitionContext no longer has an `animate` method. Instead, Motions are defined to export functions that automatically animate.
 - BREAKING: the signature for defining a Motion has changed. By convention, your default export should be function that creates and starts the motion, and you should also offer a named export for your Motion subclass so that others can extend from it.
 - BREAKING: rules functions get named arguments instead of positional arguments.
 - BREAKING: renamed animated-bind component to animated-value. "bind" made sense in the context of early Ember, it's not really a thing people say anymore.
 - BREAKING: we only provide insertedSprites at initial render if you set initialInsertion=true. Received sprites are always still provided, because that's what they're for.
 - BREAKING: moved around many internal modules to make it clear what things are publicy importable.
 - BREAKING: rename the default cosine-based easing function from `inAndOut` to `easeInAndOut` for consistency with `easeIn` and `easeOut`.
 - BREAKING: the built-in `scale` motion now adjusts initial scale correctly. Previously you needed to do it manually, but now we can make it automatic using Sprite's originalInitialBounds and originalFinalBounds.



# v0.0.1-alpha.0

First tagged released
