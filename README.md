# scala-oss-bug-hunt

A list of bugs I found in the Scala ecosystem with an AI-assisted fuzzing setup using [Idris 2](https://github.com/idris-lang/Idris2) and [DepTyCheck](https://github.com/buzden/deptycheck/).

Every bug below has a minimal, runnable reproducer (`scala-cli`, Scala 3.8.3 + latest library version). I reviewed each one by hand before opening the issue. If something turns out not to be a real bug, sorry — please let me know in the corresponding upstream issue.

## Issues filed

### [dotty-cps-async/dotty-cps-async](https://github.com/dotty-cps-async/dotty-cps-async)

- [#119](https://github.com/dotty-cps-async/dotty-cps-async/issues/119) — EitherAsyncShift.forall returns false for Left (should be true)
- [#120](https://github.com/dotty-cps-async/dotty-cps-async/issues/120) — TryAsyncShift.recover/recoverWith throw MatchError on unhandled exceptions
- [#121](https://github.com/dotty-cps-async/dotty-cps-async/issues/121) — UsingAsyncShift.apply leaks the resource on the failure path
- [#122](https://github.com/dotty-cps-async/dotty-cps-async/issues/122) — IndexedSeqAsyncShift.indexWhere ignores the from parameter
- [#123](https://github.com/dotty-cps-async/dotty-cps-async/issues/123) — ArrayOpsAsyncShift.dropWhile returns Array(head) instead of empty when all elements match

### [ghostdogpr/caliban](https://github.com/ghostdogpr/caliban)

- [#2941](https://github.com/ghostdogpr/caliban/issues/2941) — ResponseValue.ObjectValue.equals compares hashCode only — violates equals contract
- [#2942](https://github.com/ghostdogpr/caliban/issues/2942) — ResponseValue.deepMerge drops fields from the right-hand side that aren't in the left

### [Iltotore/iron](https://github.com/Iltotore/iron)

- [#369](https://github.com/Iltotore/iron/issues/369) — Not implication is the inverse, not the contrapositive (unsoundness)
- [#370](https://github.com/Iltotore/iron/issues/370) — ForAll ==> Exists (and friends) are unsound on empty/short collections
- [#371](https://github.com/Iltotore/iron/issues/371) — Numeric Greater/Less/Multiple for Int/Long compare via Double, losing precision above 2^53

### [lampepfl/gears](https://github.com/lampepfl/gears)

- [#179](https://github.com/lampepfl/gears/issues/179) — TaskSchedule.RepeatUntilFailure/Success increments by 2, causing infinite loop on even maxRepetitions

### [propensive/soundness](https://github.com/propensive/soundness)

- [#1041](https://github.com/propensive/soundness/issues/1041) — hypotenuse `addS*` overflow check misses negative-overflow cases
- [#1042](https://github.com/propensive/soundness/issues/1042) — hypotenuse `Short.**` truncates its `Double` result through `.toShort
- [#1043](https://github.com/propensive/soundness/issues/1043) — hypotenuse `Byte`/`Short` `hex`/`octal`/`binary` sign-extend to 32 bits
- [#1044](https://github.com/propensive/soundness/issues/1044) — hypotenuse `Float`/`Double` `%%` returns wrong result for negative divisors
- [#1045](https://github.com/propensive/soundness/issues/1045) — quantitative Temperature + Quantity[Rankines[1]] uses inverted 9/5 factor (should be 5/9)
- [#1046](https://github.com/propensive/soundness/issues/1046) — gossamer `levenshteinDistance` returns 0 when the left string is empty
- [#1047](https://github.com/propensive/soundness/issues/1047) — jacinta `Json.delete` allocates `Array[String]` for the values column
- [#1048](https://github.com/propensive/soundness/issues/1048) — iridescence `Hsl.saturate`/`desaturate`/`rotate`/`pure` return `Hsv` instead of `Hsl
- [#1049](https://github.com/propensive/soundness/issues/1049) — geodesy `Compass.points8` lists `Southwest` twice; `Northwest` is missing
- [#1050](https://github.com/propensive/soundness/issues/1050) — caesura `Dsv` showable only quotes cells containing the quote char, not the delimiter or newlines

### [raquo/Laminar](https://github.com/raquo/Laminar)

- [#195](https://github.com/raquo/Laminar/issues/195) — ChildrenCommandInserter.Append unconditionally sets nodeCountDiff = 1, drifting on failed inserts
- [#196](https://github.com/raquo/Laminar/issues/196) — insertChildBefore/After call setParent unconditionally on failed DOM insert

### [rcardin/raise4s](https://github.com/rcardin/raise4s)

- [#134](https://github.com/rcardin/raise4s/issues/134) — accumulate silently drops accumulated errors when no Value.value is read

### [rcardin/yaes](https://github.com/rcardin/yaes)

- [#253](https://github.com/rcardin/yaes/issues/253) — yaes-core: `Raise.catching[E]` misses subclasses of `E` (uses `==` instead of `isInstance`)
- [#254](https://github.com/rcardin/yaes/issues/254) — yaes-core: `JvmStructuredScope.scopes` uses `mutable.Map` from concurrent virtual threads
- [#255](https://github.com/rcardin/yaes/issues/255) — yaes-core: `Var` CAS loop uses Scala `==` (structural) instead of `eq` (reference) — ABA-prone

### [scalameta/munit](https://github.com/scalameta/munit)

- [#1090](https://github.com/scalameta/munit/issues/1090) — munitAppendToFailureMessage NPEs when the test exception has a null message

### [scalus3/scalus](https://github.com/scalus3/scalus)

- [#272](https://github.com/scalus3/scalus/issues/272) — NonNegativeInterval overrides equals (compares reduced fractions) but not hashCode

### [takapi327/ldbc](https://github.com/takapi327/ldbc)

- [#710](https://github.com/takapi327/ldbc/issues/710) — [Bug]: PooledDataSource.validateConnection uses handleError, dropping debug log effect
- [#711](https://github.com/takapi327/ldbc/issues/711) — [Bug]: buildBatchQuery splits on case-sensitive "VALUES", breaks for lowercase "values"
- [#712](https://github.com/takapi327/ldbc/issues/712) — [Bug]: Statement.execute throws MatchError for SHOW/DESCRIBE/EXPLAIN and other result-set queries

### [xebia-functional/Unwrapped](https://github.com/xebia-functional/Unwrapped)

- [#136](https://github.com/xebia-functional/Unwrapped/issues/136) — zipWithIndex shares its counter across stream consumptions

### [zio/zio-schema](https://github.com/zio/zio-schema)

- [#1096](https://github.com/zio/zio-schema/issues/1096) — dynamic: DynamicValue round-trip fails for Schema.Fallback (Left/Right/Both)
- [#1097](https://github.com/zio/zio-schema/issues/1097) — dynamic: DynamicValue round-trip fails for Schema.NonEmptySequence and Schema.NonEmptyMap
- [#1098](https://github.com/zio/zio-schema/issues/1098) — Patch.Temporal for ZonedDateTimeType casts to LocalDate (ClassCastException)


## How this was built

The pipeline lives in a separate working directory (94 cloned Scala projects, ~10K-iteration loop). Each candidate bug:

1. Found via static analysis or fuzzing
2. Reduced to a minimal `scala-cli` reproducer
3. Verified to compile + reproduce on Scala 3.8.3 with the latest published library version
4. Cross-checked against the project's existing issues (no duplicate filing)
5. Manually reviewed before submission

The full pipeline (`ralph-loop`, prompts, heuristics, reproducers) is private for now.

If your project doesn't accept AI-assisted issue reports, please let me know — and ideally publish a rule the way Eugene Yokota did for sbt 2.0, so contributors know up front.
