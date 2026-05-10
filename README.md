# scala-oss-bug-hunt

A list of bugs I found in the Scala ecosystem with an AI-assisted fuzzing setup using [Idris 2](https://github.com/idris-lang/Idris2) and [DepTyCheck](https://github.com/buzden/deptycheck/).

Every bug below has a minimal, runnable reproducer (`scala-cli`, Scala 3.8.3 + latest library version). If something turns out not to be a real bug, sorry — please let me know in the corresponding upstream issue.

## Issues filed

### [com-lihaoyi/scalasql](https://github.com/com-lihaoyi/scalasql)

- [#113](https://github.com/com-lihaoyi/scalasql/issues/113) — take(m).drop(n) with n > m generates negative LIMIT, rejected by every supported dialect

### [com-lihaoyi/upickle](https://github.com/com-lihaoyi/upickle)

- [#702](https://github.com/com-lihaoyi/upickle/issues/702) — MsgPackReader silently returns empty Array/Map for Array32/Map32 with length >= 2^31

### [dotty-cps-async/dotty-cps-async](https://github.com/dotty-cps-async/dotty-cps-async)

- [#119](https://github.com/dotty-cps-async/dotty-cps-async/issues/119) — EitherAsyncShift.forall returns false for Left (should be true)
- [#120](https://github.com/dotty-cps-async/dotty-cps-async/issues/120) — TryAsyncShift.recover/recoverWith throw MatchError on unhandled exceptions
- [#121](https://github.com/dotty-cps-async/dotty-cps-async/issues/121) — UsingAsyncShift.apply leaks the resource on the failure path
- [#122](https://github.com/dotty-cps-async/dotty-cps-async/issues/122) — IndexedSeqAsyncShift.indexWhere ignores the from parameter
- [#123](https://github.com/dotty-cps-async/dotty-cps-async/issues/123) — ArrayOpsAsyncShift.dropWhile returns Array(head) instead of empty when all elements match
- [#124](https://github.com/dotty-cps-async/dotty-cps-async/issues/124) — BreaksAsyncShift.breakable discards the body computation via value-discarding to Unit
- [#125](https://github.com/dotty-cps-async/dotty-cps-async/issues/125) — ArrayOpsAsyncShift.lastIndexWhere doesn't clamp end, throws IndexOutOfBoundsException

### [ghostdogpr/caliban](https://github.com/ghostdogpr/caliban)

- [#2941](https://github.com/ghostdogpr/caliban/issues/2941) — ResponseValue.ObjectValue.equals compares hashCode only — violates equals contract
- [#2942](https://github.com/ghostdogpr/caliban/issues/2942) — ResponseValue.deepMerge drops fields from the right-hand side that aren't in the left
- [#2943](https://github.com/ghostdogpr/caliban/issues/2943) — GraphQLResponse.withExtension creates duplicate keys instead of replacing
- [#2944](https://github.com/ghostdogpr/caliban/issues/2944) — StringValue.toString and EnumValue.toString skip backslash, backtick, tab, backspace and form-feed escapes
- [#2945](https://github.com/ghostdogpr/caliban/issues/2945) — Connection.fromList returns wrong hasPreviousPage / hasNextPage when paginating with cursor
- [#2946](https://github.com/ghostdogpr/caliban/issues/2946) — Field.resolveVariables silently drops arguments backed by nullable variables with no value
- [#2947](https://github.com/ghostdogpr/caliban/issues/2947) — validateSubscriptionOperation only checks the first subscription operation in the document

### [http4s/http4s](https://github.com/http4s/http4s)

- [#7835](https://github.com/http4s/http4s/issues/7835) — HttpDate.fromInstant truncates negative epochs toward zero, off by one second before 1970
- [#7836](https://github.com/http4s/http4s/issues/7836) — Content-Range parser and constructor accept invalid ranges where first > last
- [#7837](https://github.com/http4s/http4s/issues/7837) — Set-Cookie Max-Age parser rejects negative values that RFC 6265 specifies as valid
- [#7838](https://github.com/http4s/http4s/issues/7838) — UriCoding.encode sign-extends bytes >= 0x80 when calling toSkip, breaking custom predicates for non-ASCII
- [#7839](https://github.com/http4s/http4s/issues/7839) — HttpsRedirect middleware bakes the port into the hostname (or drops it entirely) in the redirect Location
- [#7840](https://github.com/http4s/http4s/issues/7840) — CORS default policy allows PUT/PATCH/DELETE despite docstring saying GET, HEAD, POST only
- [#7841](https://github.com/http4s/http4s/issues/7841) — RelaxedCookies parser accepts DEL (0x7F) and C1 control characters in cookie values
- [#7842](https://github.com/http4s/http4s/issues/7842) — Keep-Alive reservedTokens has typo "token" instead of "timeout"
- [#7843](https://github.com/http4s/http4s/issues/7843) — Retry-After delay-seconds parser throws NumberFormatException on overflow instead of returning ParseFailure
- [#7844](https://github.com/http4s/http4s/issues/7844) — Host header constructor and parser accept invalid port numbers (negative, > 65535)
- [#7845](https://github.com/http4s/http4s/issues/7845) — VirtualHost.wildcard allows regex injection through unescaped metacharacters
- [#7846](https://github.com/http4s/http4s/issues/7846) — Caching middleware Expires arithmetic can overflow Long for large but finite lifetimes
- [#7847](https://github.com/http4s/http4s/issues/7847) — Throttle.defaultResponse silently drops the retryAfter parameter — no Retry-After header on 429
- [#7848](https://github.com/http4s/http4s/issues/7848) — VirtualHost.regex uses partial match instead of full match — host header spoofing
- [#7849](https://github.com/http4s/http4s/issues/7849) — Access-Control-Max-Age.Cache.apply bypasses the validation in fromLong

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
- [#1051](https://github.com/propensive/soundness/issues/1051) — parasite Task.apply silently ignores the daemon parameter, hardcodes daemon = false
- [#1052](https://github.com/propensive/soundness/issues/1052) — parasite Promise.await(duration) passes relative nanos to LockSupport.parkUntil (expects absolute millis)
- [#1053](https://github.com/propensive/soundness/issues/1053) — feudalism Semaphore.access / Semaphore.isolate use notify() instead of notifyAll() — lost wakeups
- [#1054](https://github.com/propensive/soundness/issues/1054) — hallucination Raster.crop swaps top/bottom in the pixel mapping
- [#1055](https://github.com/propensive/soundness/issues/1055) — profanity Signal.id formula returns wrong POSIX numbers (SIGHUP becomes -1)
- [#1056](https://github.com/propensive/soundness/issues/1056) — telekinesis Context backs session storage with an unsynchronised mutable HashMap
- [#1057](https://github.com/propensive/soundness/issues/1057) — gastronomy Long Digestible uses wrong shift range and loses two bytes per Long
- [#1058](https://github.com/propensive/soundness/issues/1058) — denominative Ordinal.subsequent(size) returns an Interval of size+1 (off-by-one)
- [#1059](https://github.com/propensive/soundness/issues/1059) — revolution manifestAttributes objects misspell ``SpecificationVendor`` / ``SpecificationVersion`` as ``Specifacation*
- [#1060](https://github.com/propensive/soundness/issues/1060) — acyclicity Dag.sort uses unsafe .get and crashes with NoSuchElementException on cyclic graphs
- [#1061](https://github.com/propensive/soundness/issues/1061) — revolution Semver ordering is wrong for equal versions and for release-vs-prerelease

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

### [sirthias/borer](https://github.com/sirthias/borer)

- [#829](https://github.com/sirthias/borer/issues/829) — Reader.longCompare returns the wrong sign due to Long subtraction overflow

### [takapi327/ldbc](https://github.com/takapi327/ldbc)

- [#710](https://github.com/takapi327/ldbc/issues/710) — [Bug]: PooledDataSource.validateConnection uses handleError, dropping debug log effect
- [#711](https://github.com/takapi327/ldbc/issues/711) — [Bug]: buildBatchQuery splits on case-sensitive "VALUES", breaks for lowercase "values"
- [#712](https://github.com/takapi327/ldbc/issues/712) — [Bug]: Statement.execute throws MatchError for SHOW/DESCRIBE/EXPLAIN and other result-set queries

### [typelevel/fs2](https://github.com/typelevel/fs2)

- [#3725](https://github.com/typelevel/fs2/issues/3725) — text.linesLimited lets through arbitrarily long lines when the line and its terminator land in the same chunk

### [typelevel/skunk](https://github.com/typelevel/skunk)

- [#1295](https://github.com/typelevel/skunk/issues/1295) — timestamptz precision error message has typo "timestampz" (missing "t")

### [wvlet/wvlet](https://github.com/wvlet/wvlet)

- [#1697](https://github.com/wvlet/wvlet/issues/1697) — doubleQuoteIfNecessary doesn't escape internal double quotes, producing malformed SQL identifiers
- [#1698](https://github.com/wvlet/wvlet/issues/1698) — TripleQuoteString.sqlExpr drops embedded newlines from triple-quoted string literals

### [xebia-functional/Unwrapped](https://github.com/xebia-functional/Unwrapped)

- [#136](https://github.com/xebia-functional/Unwrapped/issues/136) — zipWithIndex shares its counter across stream consumptions

### [zio/zio](https://github.com/zio/zio)

- [#10883](https://github.com/zio/zio/issues/10883) — Schedule.dayOfMonth(30) crashes with DateTimeException in months that don't have day 30

### [zio/zio-protoquill](https://github.com/zio/zio-protoquill)

- [#747](https://github.com/zio/zio-protoquill/issues/747) — transaction commit/rollback wrapped in ZIO.succeed turns JDBC errors into unhandled defects
- [#748](https://github.com/zio/zio-protoquill/issues/748) — JdbcContext.probe leaks the JDBC Statement (never closed)

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
