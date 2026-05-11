# scala-oss-bug-hunt

A list of bugs I found in the Scala ecosystem with an AI-assisted fuzzing setup using [Idris 2](https://github.com/idris-lang/Idris2) and [DepTyCheck](https://github.com/buzden/deptycheck/).

Every bug below has a minimal, runnable reproducer (`scala-cli`, Scala 3.8.3 + latest library version). If something turns out not to be a real bug, sorry — just close it; I monitor every issue and will pick it up.

## Issues filed

### [armanbilge/calico](https://github.com/armanbilge/calico)

![status](https://img.shields.io/github/issues/detail/state/armanbilge/calico/470)
- [#470](https://github.com/armanbilge/calico/issues/470) — KeyedChildren publishes the new active map before new nodes are acquired

### [AugustNagro/magnum](https://github.com/AugustNagro/magnum)

![status](https://img.shields.io/github/issues/detail/state/AugustNagro/magnum/148)
- [#148](https://github.com/AugustNagro/magnum/issues/148) — Transactor.transact catches every Throwable, including OOM and StackOverflow
![status](https://img.shields.io/github/issues/detail/state/AugustNagro/magnum/149)
- [#149](https://github.com/AugustNagro/magnum/issues/149) — ScalaBigDecimalCodec.readSingle throws on SQL NULL instead of returning null
![status](https://img.shields.io/github/issues/detail/state/AugustNagro/magnum/150)
- [#150](https://github.com/AugustNagro/magnum/issues/150) — Spec.orderBy / seek concatenate raw column names into SQL
![status](https://img.shields.io/github/issues/detail/state/AugustNagro/magnum/151)
- [#151](https://github.com/AugustNagro/magnum/issues/151) — MagUser test fixture overrides equals but not hashCode (only affects tests)

### [business4s/decisions4s](https://github.com/business4s/decisions4s)

![status](https://img.shields.io/github/issues/detail/state/business4s/decisions4s/101)
- [#101](https://github.com/business4s/decisions4s/issues/101) — MarkdownRenderer emits rows with inconsistent column counts when annotations are mixed
![status](https://img.shields.io/github/issues/detail/state/business4s/decisions4s/102)
- [#102](https://github.com/business4s/decisions4s/issues/102) — Distinct hit policy uses Set deduplication, can silently accept +0.0 vs -0.0 as identical
![status](https://img.shields.io/github/issues/detail/state/business4s/decisions4s/103)
- [#103](https://github.com/business4s/decisions4s/issues/103) — DiagnosticsPrinter throws empty.max when constructed for a decision table with zero input fields
![status](https://img.shields.io/github/issues/detail/state/business4s/decisions4s/104)
- [#104](https://github.com/business4s/decisions4s/issues/104) — FromFeel numeric readers throw bare MatchError on non-numeric inputs, no field/expression context

### [business4s/workflows4s](https://github.com/business4s/workflows4s)

![status](https://img.shields.io/github/issues/detail/state/business4s/workflows4s/257)
- [#257](https://github.com/business4s/workflows4s/issues/257) — ProceedingVisitor.onParallel calls .get on Option that can be None when one branch errored and another is still partial
![status](https://img.shields.io/github/issues/detail/state/business4s/workflows4s/258)
- [#258](https://github.com/business4s/workflows4s/issues/258) — extractFirstInterruption drops the third step in 3-element interruption sequences (off-by-one threshold)
![status](https://img.shields.io/github/issues/detail/state/business4s/workflows4s/259)
- [#259](https://github.com/business4s/workflows4s/issues/259) — RenderUtils.hasStarted returns true for a Loop that hasn't started any iteration

### [circe/circe](https://github.com/circe/circe)

![status](https://img.shields.io/github/issues/detail/state/circe/circe/2457)
- [#2457](https://github.com/circe/circe/issues/2457) — BiggerDecimal.integralIsValidLong returns true for "-", "+", "a" and crashes on ""
![status](https://img.shields.io/github/issues/detail/state/circe/circe/2458)
- [#2458](https://github.com/circe/circe/issues/2458) — Printer with empty indent swaps rbraceLeft and rbraceRight (ConstantPieces path)
![status](https://img.shields.io/github/issues/detail/state/circe/circe/2459)
- [#2459](https://github.com/circe/circe/issues/2459) — Printer indents content after `}` and `]` at child depth instead of parent depth

### [com-lihaoyi/fansi](https://github.com/com-lihaoyi/fansi)

![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/fansi/139)
- [#139](https://github.com/com-lihaoyi/fansi/issues/139) — Str.overlayAll error message prints end where start should appear
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/fansi/140)
- [#140](https://github.com/com-lihaoyi/fansi/issues/140) — Attrs.Multiple.equals uses reference equality on attrs while hashCode is structural

### [com-lihaoyi/geny](https://github.com/com-lihaoyi/geny)

![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/geny/104)
- [#104](https://github.com/com-lihaoyi/geny/issues/104) — Bytes overrides equals but not hashCode, breaking HashMap/HashSet
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/geny/105)
- [#105](https://github.com/com-lihaoyi/geny/issues/105) — Generator.maxBy / minBy silently return null on empty generators

### [com-lihaoyi/scalasql](https://github.com/com-lihaoyi/scalasql)

![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/scalasql/113)
- [#113](https://github.com/com-lihaoyi/scalasql/issues/113) — take(m).drop(n) with n > m generates negative LIMIT, rejected by every supported dialect
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/scalasql/114)
- [#114](https://github.com/com-lihaoyi/scalasql/issues/114) — onConflictUpdate with no update assignments emits invalid SQL ("DO UPDATE SET")
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/scalasql/115)
- [#115](https://github.com/com-lihaoyi/scalasql/issues/115) — OptionType.put always passes JDBCType.NULL to setNull, ignoring the column's actual JDBC type
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/scalasql/116)
- [#116](https://github.com/com-lihaoyi/scalasql/issues/116) — Config.camelToSnake merges consecutive uppercase letters (XMLParser -> xmlparser, not xml_parser)
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/scalasql/117)
- [#117](https://github.com/com-lihaoyi/scalasql/issues/117) — WithCte.filter swaps lhs/rhs — WHERE ends up inside the CTE body, not on the outer query
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/scalasql/118)
- [#118](https://github.com/com-lihaoyi/scalasql/issues/118) — startsWith / endsWith / contains do not escape LIKE wildcards in user input
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/scalasql/119)
- [#119](https://github.com/com-lihaoyi/scalasql/issues/119) — Identifier escape() in every dialect leaves inner delimiter chars unescaped

### [com-lihaoyi/upickle](https://github.com/com-lihaoyi/upickle)

![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/upickle/702)
- [#702](https://github.com/com-lihaoyi/upickle/issues/702) — MsgPackReader silently returns empty Array/Map for Array32/Map32 with length >= 2^31
![status](https://img.shields.io/github/issues/detail/state/com-lihaoyi/upickle/703)
- [#703](https://github.com/com-lihaoyi/upickle/issues/703) — ujson silently accepts invalid hex digits in \uXXXX escapes (g, X, Z map to 0)

### [dotty-cps-async/dotty-cps-async](https://github.com/dotty-cps-async/dotty-cps-async)

![status](https://img.shields.io/github/issues/detail/state/dotty-cps-async/dotty-cps-async/119)
- [#119](https://github.com/dotty-cps-async/dotty-cps-async/issues/119) — EitherAsyncShift.forall returns false for Left (should be true)
![status](https://img.shields.io/github/issues/detail/state/dotty-cps-async/dotty-cps-async/120)
- [#120](https://github.com/dotty-cps-async/dotty-cps-async/issues/120) — TryAsyncShift.recover/recoverWith throw MatchError on unhandled exceptions
![status](https://img.shields.io/github/issues/detail/state/dotty-cps-async/dotty-cps-async/121)
- [#121](https://github.com/dotty-cps-async/dotty-cps-async/issues/121) — UsingAsyncShift.apply leaks the resource on the failure path
![status](https://img.shields.io/github/issues/detail/state/dotty-cps-async/dotty-cps-async/122)
- [#122](https://github.com/dotty-cps-async/dotty-cps-async/issues/122) — IndexedSeqAsyncShift.indexWhere ignores the from parameter
![status](https://img.shields.io/github/issues/detail/state/dotty-cps-async/dotty-cps-async/123)
- [#123](https://github.com/dotty-cps-async/dotty-cps-async/issues/123) — ArrayOpsAsyncShift.dropWhile returns Array(head) instead of empty when all elements match
![status](https://img.shields.io/github/issues/detail/state/dotty-cps-async/dotty-cps-async/124)
- [#124](https://github.com/dotty-cps-async/dotty-cps-async/issues/124) — BreaksAsyncShift.breakable discards the body computation via value-discarding to Unit
![status](https://img.shields.io/github/issues/detail/state/dotty-cps-async/dotty-cps-async/125)
- [#125](https://github.com/dotty-cps-async/dotty-cps-async/issues/125) — ArrayOpsAsyncShift.lastIndexWhere doesn't clamp end, throws IndexOutOfBoundsException

### [EmergentOrder/onnx-scala](https://github.com/EmergentOrder/onnx-scala)

![status](https://img.shields.io/github/issues/detail/state/EmergentOrder/onnx-scala/538)
- [#538](https://github.com/EmergentOrder/onnx-scala/issues/538) — ONNXHelper.outputs filter is always false because nodes is Seq[Iterable[String]] and contains takes a String
![status](https://img.shields.io/github/issues/detail/state/EmergentOrder/onnx-scala/539)
- [#539](https://github.com/EmergentOrder/onnx-scala/issues/539) — TileV13 builds the repeats array from repeats.indices instead of repeats values, so every Tile op gets [0, 1, 2, …]
![status](https://img.shields.io/github/issues/detail/state/EmergentOrder/onnx-scala/540)
- [#540](https://github.com/EmergentOrder/onnx-scala/issues/540) — onnxTensorProtoToArray throws MatchError on BOOL, STRING, UINT*, FLOAT16, BFLOAT16 and COMPLEX tensors

### [flink-extended/flink-scala-api](https://github.com/flink-extended/flink-scala-api)

![status](https://img.shields.io/github/issues/detail/state/flink-extended/flink-scala-api/372)
- [#372](https://github.com/flink-extended/flink-scala-api/issues/372) — EitherTypeInfo.equals / hashCode NPE when leftTypeInfo or rightTypeInfo is null
![status](https://img.shields.io/github/issues/detail/state/flink-extended/flink-scala-api/373)
- [#373](https://github.com/flink-extended/flink-scala-api/issues/373) — MappedTypeInformation.hashCode ignores mapper, equals checks both — contract violation and systematic collisions
![status](https://img.shields.io/github/issues/detail/state/flink-extended/flink-scala-api/374)
- [#374](https://github.com/flink-extended/flink-scala-api/issues/374) — OptionTypeInfo.createComparator throws with truncated message "Element type that doesn't support "
![status](https://img.shields.io/github/issues/detail/state/flink-extended/flink-scala-api/375)
- [#375](https://github.com/flink-extended/flink-scala-api/issues/375) — CoproductSerializer subtype-index byte overflow for sealed traits with >127 subtypes

### [FunktionalIO/pillars](https://github.com/FunktionalIO/pillars)

![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/259)
- [#259](https://github.com/FunktionalIO/pillars/issues/259) — rabbitmq-fs2` config conversion silently drops `automaticTopologyRecovery
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/260)
- [#260](https://github.com/FunktionalIO/pillars/issues/260) — flags` `FlagNotFound` error message is missing a space — `Flag my-featurenot found
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/261)
- [#261](https://github.com/FunktionalIO/pillars/issues/261) — Metrics` response-body-size recorder discards its `IO` via `Option.foreach
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/262)
- [#262](https://github.com/FunktionalIO/pillars/issues/262) — db-skunk RedactionStrategy encoder writes "OptIn" while the decoder lowercases input and matches "optin"
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/263)
- [#263](https://github.com/FunktionalIO/pillars/issues/263) — Metrics.responseBodySize double-wraps m.eval, so the recorder.record IO is never run
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/264)
- [#264](https://github.com/FunktionalIO/pillars/issues/264) — HTTP client metrics middleware never records request or response body size histograms
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/265)
- [#265](https://github.com/FunktionalIO/pillars/issues/265) — db-skunk SSL CirceEncoder only handles None, Trusted, System and crashes with MatchError on custom SSL contexts
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/266)
- [#266](https://github.com/FunktionalIO/pillars/issues/266) — migrateModule sanitization produces table names with `-`, which violates the DatabaseTable constraint (silently, via `.assume`)
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/267)
- [#267](https://github.com/FunktionalIO/pillars/issues/267) — db-doobie DatabaseConfig.toHikariConfig silently drops systemSchema, appSchema, and debug
![status](https://img.shields.io/github/issues/detail/state/FunktionalIO/pillars/268)
- [#268](https://github.com/FunktionalIO/pillars/issues/268) — db-skunk Typer.Strategy encoder emits MixedCase, decoder lowercases — round-trip OK but inconsistent with rest of codec

### [ghostdogpr/caliban](https://github.com/ghostdogpr/caliban)

![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2941)
- [#2941](https://github.com/ghostdogpr/caliban/issues/2941) — ResponseValue.ObjectValue.equals compares hashCode only — violates equals contract
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2942)
- [#2942](https://github.com/ghostdogpr/caliban/issues/2942) — ResponseValue.deepMerge drops fields from the right-hand side that aren't in the left
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2943)
- [#2943](https://github.com/ghostdogpr/caliban/issues/2943) — GraphQLResponse.withExtension creates duplicate keys instead of replacing
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2944)
- [#2944](https://github.com/ghostdogpr/caliban/issues/2944) — StringValue.toString and EnumValue.toString skip backslash, backtick, tab, backspace and form-feed escapes
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2945)
- [#2945](https://github.com/ghostdogpr/caliban/issues/2945) — Connection.fromList returns wrong hasPreviousPage / hasNextPage when paginating with cursor
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2946)
- [#2946](https://github.com/ghostdogpr/caliban/issues/2946) — Field.resolveVariables silently drops arguments backed by nullable variables with no value
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2947)
- [#2947](https://github.com/ghostdogpr/caliban/issues/2947) — validateSubscriptionOperation only checks the first subscription operation in the document
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2948)
- [#2948](https://github.com/ghostdogpr/caliban/issues/2948) — FragmentValidator caches keyed only by hashCode — collisions can flip validation result
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2949)
- [#2949](https://github.com/ghostdogpr/caliban/issues/2949) — SchemaComparison.compareDirectives flags unchanged arguments as changed when any sibling argument differs
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2950)
- [#2950](https://github.com/ghostdogpr/caliban/issues/2950) — RemoteSchema.parseRemoteSchema always sets subscriptionType to None
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2951)
- [#2951](https://github.com/ghostdogpr/caliban/issues/2951) — RemoteResolver.unwrap silently drops every field except the first from a multi-field ObjectValue
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2952)
- [#2952](https://github.com/ghostdogpr/caliban/issues/2952) — SchemaTracer wrapper calls .head on potentially empty fields list
![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/caliban/2953)
- [#2953](https://github.com/ghostdogpr/caliban/issues/2953) — ReportingDaemon halts the schema reporting loop on SchemaError, ignoring inSeconds retry hint

### [ghostdogpr/purelogic](https://github.com/ghostdogpr/purelogic)

![status](https://img.shields.io/github/issues/detail/state/ghostdogpr/purelogic/26)
- [#26](https://github.com/ghostdogpr/purelogic/issues/26) — recoverSomeKeepLog rolls back state but keeps log when the partial function does not match, leaving inconsistent state

### [hedgehogqa/scala-hedgehog](https://github.com/hedgehogqa/scala-hedgehog)

![status](https://img.shields.io/github/issues/detail/state/hedgehogqa/scala-hedgehog/307)
- [#307](https://github.com/hedgehogqa/scala-hedgehog/issues/307) — Seed.chooseLong overflows max - min + 2 and computes x % range + min - 1, producing values below min
![status](https://img.shields.io/github/issues/detail/state/hedgehogqa/scala-hedgehog/308)
- [#308](https://github.com/hedgehogqa/scala-hedgehog/issues/308) — MersenneTwister64.hashCode only uses mti, ignoring the 312-element mt array

### [http4s/http4s](https://github.com/http4s/http4s)

![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7835)
- [#7835](https://github.com/http4s/http4s/issues/7835) — HttpDate.fromInstant truncates negative epochs toward zero, off by one second before 1970
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7836)
- [#7836](https://github.com/http4s/http4s/issues/7836) — Content-Range parser and constructor accept invalid ranges where first > last
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7837)
- [#7837](https://github.com/http4s/http4s/issues/7837) — Set-Cookie Max-Age parser rejects negative values that RFC 6265 specifies as valid
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7838)
- [#7838](https://github.com/http4s/http4s/issues/7838) — UriCoding.encode sign-extends bytes >= 0x80 when calling toSkip, breaking custom predicates for non-ASCII
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7839)
- [#7839](https://github.com/http4s/http4s/issues/7839) — HttpsRedirect middleware bakes the port into the hostname (or drops it entirely) in the redirect Location
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7840)
- [#7840](https://github.com/http4s/http4s/issues/7840) — CORS default policy allows PUT/PATCH/DELETE despite docstring saying GET, HEAD, POST only
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7841)
- [#7841](https://github.com/http4s/http4s/issues/7841) — RelaxedCookies parser accepts DEL (0x7F) and C1 control characters in cookie values
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7842)
- [#7842](https://github.com/http4s/http4s/issues/7842) — Keep-Alive reservedTokens has typo "token" instead of "timeout"
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7843)
- [#7843](https://github.com/http4s/http4s/issues/7843) — Retry-After delay-seconds parser throws NumberFormatException on overflow instead of returning ParseFailure
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7844)
- [#7844](https://github.com/http4s/http4s/issues/7844) — Host header constructor and parser accept invalid port numbers (negative, > 65535)
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7845)
- [#7845](https://github.com/http4s/http4s/issues/7845) — VirtualHost.wildcard allows regex injection through unescaped metacharacters
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7846)
- [#7846](https://github.com/http4s/http4s/issues/7846) — Caching middleware Expires arithmetic can overflow Long for large but finite lifetimes
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7847)
- [#7847](https://github.com/http4s/http4s/issues/7847) — Throttle.defaultResponse silently drops the retryAfter parameter — no Retry-After header on 429
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7848)
- [#7848](https://github.com/http4s/http4s/issues/7848) — VirtualHost.regex uses partial match instead of full match — host header spoofing
![status](https://img.shields.io/github/issues/detail/state/http4s/http4s/7849)
- [#7849](https://github.com/http4s/http4s/issues/7849) — Access-Control-Max-Age.Cache.apply bypasses the validation in fromLong

### [Iltotore/iron](https://github.com/Iltotore/iron)

![status](https://img.shields.io/github/issues/detail/state/Iltotore/iron/369)
- [#369](https://github.com/Iltotore/iron/issues/369) — Not implication is the inverse, not the contrapositive (unsoundness)
![status](https://img.shields.io/github/issues/detail/state/Iltotore/iron/370)
- [#370](https://github.com/Iltotore/iron/issues/370) — ForAll ==> Exists (and friends) are unsound on empty/short collections
![status](https://img.shields.io/github/issues/detail/state/Iltotore/iron/371)
- [#371](https://github.com/Iltotore/iron/issues/371) — Numeric Greater/Less/Multiple for Int/Long compare via Double, losing precision above 2^53

### [kitlangton/neotype](https://github.com/kitlangton/neotype)

![status](https://img.shields.io/github/issues/detail/state/kitlangton/neotype/465)
- [#465](https://github.com/kitlangton/neotype/issues/465) — CaseClassBuilder.newInstance silently swallows constructor exceptions and returns a fake value
![status](https://img.shields.io/github/issues/detail/state/kitlangton/neotype/466)
- [#466](https://github.com/kitlangton/neotype/issues/466) — LambdaCompiler.isDefinedAt silently turns Left(error) into false — collect/filter/exists drop elements without surfacing comptime errors
![status](https://img.shields.io/github/issues/detail/state/kitlangton/neotype/467)
- [#467](https://github.com/kitlangton/neotype/issues/467) — TermCompiler — TermIR.Throw uses raw throw inside flatMap, bypassing the Either error pipeline
![status](https://img.shields.io/github/issues/detail/state/kitlangton/neotype/468)
- [#468](https://github.com/kitlangton/neotype/issues/468) — comptime LambdaCompiler discards match scrutinee — `(x => f(x) match ...)` matches against `x`, not `f(x)

### [lampepfl/gears](https://github.com/lampepfl/gears)

![status](https://img.shields.io/github/issues/detail/state/lampepfl/gears/179)
- [#179](https://github.com/lampepfl/gears/issues/179) — TaskSchedule.RepeatUntilFailure/Success increments by 2, causing infinite loop on even maxRepetitions

### [lloydmeta/enumeratum](https://github.com/lloydmeta/enumeratum)

![status](https://img.shields.io/github/issues/detail/state/lloydmeta/enumeratum/469)
- [#469](https://github.com/lloydmeta/enumeratum/issues/469) — Slick CharEnum codec calls .head on the DB string and crashes on empty values

### [mattlianje/etl4s](https://github.com/mattlianje/etl4s)

![status](https://img.shields.io/github/issues/detail/state/mattlianje/etl4s/20)
- [#20](https://github.com/mattlianje/etl4s/issues/20) — Lineage JSON output produces invalid JSON when names/descriptions contain quotes, backslashes or newlines
![status](https://img.shields.io/github/issues/detail/state/mattlianje/etl4s/21)
- [#21](https://github.com/mattlianje/etl4s/issues/21) — Lineage.chain and Lineage.combine have identical implementations

### [optics-dev/Monocle](https://github.com/optics-dev/Monocle)

![status](https://img.shields.io/github/issues/detail/state/optics-dev/Monocle/1582)
- [#1582](https://github.com/optics-dev/Monocle/issues/1582) — monocle.std.string.stringToLong accepts "-0" and other negative-zero forms, breaks Prism law

### [propensive/soundness](https://github.com/propensive/soundness)

![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1041)
- [#1041](https://github.com/propensive/soundness/issues/1041) — hypotenuse `addS*` overflow check misses negative-overflow cases
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1042)
- [#1042](https://github.com/propensive/soundness/issues/1042) — hypotenuse `Short.**` truncates its `Double` result through `.toShort
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1043)
- [#1043](https://github.com/propensive/soundness/issues/1043) — hypotenuse `Byte`/`Short` `hex`/`octal`/`binary` sign-extend to 32 bits
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1044)
- [#1044](https://github.com/propensive/soundness/issues/1044) — hypotenuse `Float`/`Double` `%%` returns wrong result for negative divisors
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1045)
- [#1045](https://github.com/propensive/soundness/issues/1045) — quantitative Temperature + Quantity[Rankines[1]] uses inverted 9/5 factor (should be 5/9)
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1046)
- [#1046](https://github.com/propensive/soundness/issues/1046) — gossamer `levenshteinDistance` returns 0 when the left string is empty
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1047)
- [#1047](https://github.com/propensive/soundness/issues/1047) — jacinta `Json.delete` allocates `Array[String]` for the values column
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1048)
- [#1048](https://github.com/propensive/soundness/issues/1048) — iridescence `Hsl.saturate`/`desaturate`/`rotate`/`pure` return `Hsv` instead of `Hsl
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1049)
- [#1049](https://github.com/propensive/soundness/issues/1049) — geodesy `Compass.points8` lists `Southwest` twice; `Northwest` is missing
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1050)
- [#1050](https://github.com/propensive/soundness/issues/1050) — caesura `Dsv` showable only quotes cells containing the quote char, not the delimiter or newlines
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1051)
- [#1051](https://github.com/propensive/soundness/issues/1051) — parasite Task.apply silently ignores the daemon parameter, hardcodes daemon = false
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1052)
- [#1052](https://github.com/propensive/soundness/issues/1052) — parasite Promise.await(duration) passes relative nanos to LockSupport.parkUntil (expects absolute millis)
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1053)
- [#1053](https://github.com/propensive/soundness/issues/1053) — feudalism Semaphore.access / Semaphore.isolate use notify() instead of notifyAll() — lost wakeups
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1054)
- [#1054](https://github.com/propensive/soundness/issues/1054) — hallucination Raster.crop swaps top/bottom in the pixel mapping
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1055)
- [#1055](https://github.com/propensive/soundness/issues/1055) — profanity Signal.id formula returns wrong POSIX numbers (SIGHUP becomes -1)
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1056)
- [#1056](https://github.com/propensive/soundness/issues/1056) — telekinesis Context backs session storage with an unsynchronised mutable HashMap
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1057)
- [#1057](https://github.com/propensive/soundness/issues/1057) — gastronomy Long Digestible uses wrong shift range and loses two bytes per Long
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1058)
- [#1058](https://github.com/propensive/soundness/issues/1058) — denominative Ordinal.subsequent(size) returns an Interval of size+1 (off-by-one)
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1059)
- [#1059](https://github.com/propensive/soundness/issues/1059) — revolution manifestAttributes objects misspell ``SpecificationVendor`` / ``SpecificationVersion`` as ``Specifacation*
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1060)
- [#1060](https://github.com/propensive/soundness/issues/1060) — acyclicity Dag.sort uses unsafe .get and crashes with NoSuchElementException on cyclic graphs
![status](https://img.shields.io/github/issues/detail/state/propensive/soundness/1061)
- [#1061](https://github.com/propensive/soundness/issues/1061) — revolution Semver ordering is wrong for equal versions and for release-vs-prerelease

### [raquo/Laminar](https://github.com/raquo/Laminar)

![status](https://img.shields.io/github/issues/detail/state/raquo/Laminar/195)
- [#195](https://github.com/raquo/Laminar/issues/195) — ChildrenCommandInserter.Append unconditionally sets nodeCountDiff = 1, drifting on failed inserts
![status](https://img.shields.io/github/issues/detail/state/raquo/Laminar/196)
- [#196](https://github.com/raquo/Laminar/issues/196) — insertChildBefore/After call setParent unconditionally on failed DOM insert

### [rcardin/raise4s](https://github.com/rcardin/raise4s)

![status](https://img.shields.io/github/issues/detail/state/rcardin/raise4s/134)
- [#134](https://github.com/rcardin/raise4s/issues/134) — accumulate silently drops accumulated errors when no Value.value is read

### [rcardin/yaes](https://github.com/rcardin/yaes)

![status](https://img.shields.io/github/issues/detail/state/rcardin/yaes/253)
- [#253](https://github.com/rcardin/yaes/issues/253) — yaes-core: `Raise.catching[E]` misses subclasses of `E` (uses `==` instead of `isInstance`)
![status](https://img.shields.io/github/issues/detail/state/rcardin/yaes/254)
- [#254](https://github.com/rcardin/yaes/issues/254) — yaes-core: `JvmStructuredScope.scopes` uses `mutable.Map` from concurrent virtual threads
![status](https://img.shields.io/github/issues/detail/state/rcardin/yaes/255)
- [#255](https://github.com/rcardin/yaes/issues/255) — yaes-core: `Var` CAS loop uses Scala `==` (structural) instead of `eq` (reference) — ABA-prone

### [scala/scala3](https://github.com/scala/scala3)

![status](https://img.shields.io/github/issues/detail/state/scala/scala3/26037)
- [#26037](https://github.com/scala/scala3/issues/26037) — Crash: AssertionError "asTerm called on not-a-Term type T" when exporting members of a cyclic opaque type companion

### [scalameta/munit](https://github.com/scalameta/munit)

![status](https://img.shields.io/github/issues/detail/state/scalameta/munit/1090)
- [#1090](https://github.com/scalameta/munit/issues/1090) — munitAppendToFailureMessage NPEs when the test exception has a null message

### [scalus3/scalus](https://github.com/scalus3/scalus)

![status](https://img.shields.io/github/issues/detail/state/scalus3/scalus/272)
- [#272](https://github.com/scalus3/scalus/issues/272) — NonNegativeInterval overrides equals (compares reduced fractions) but not hashCode
![status](https://img.shields.io/github/issues/detail/state/scalus3/scalus/273)
- [#273](https://github.com/scalus3/scalus/issues/273) — BLS12-381 G1Element / G2Element / MLResult override equals without hashCode

### [siriusxm/snapshot4s](https://github.com/siriusxm/snapshot4s)

![status](https://img.shields.io/github/issues/detail/state/siriusxm/snapshot4s/203)
- [#203](https://github.com/siriusxm/snapshot4s/issues/203) — Hashing.calculateHash uses String.hashCode for patch integrity, which collides easily on a 32-bit hash
![status](https://img.shields.io/github/issues/detail/state/siriusxm/snapshot4s/204)
- [#204](https://github.com/siriusxm/snapshot4s/issues/204) — InlineRepr.printChar maps ESC (0x1B) to an empty string, silently dropping ANSI escapes from snapshot reprs
![status](https://img.shields.io/github/issues/detail/state/siriusxm/snapshot4s/205)
- [#205](https://github.com/siriusxm/snapshot4s/issues/205) — sourceBaseDirectory crashes with empty.reduce when sourceDirectories is empty, and sharedParent can NPE on disjoint paths

### [sirthias/borer](https://github.com/sirthias/borer)

![status](https://img.shields.io/github/issues/detail/state/sirthias/borer/829)
- [#829](https://github.com/sirthias/borer/issues/829) — Reader.longCompare returns the wrong sign due to Long subtraction overflow

### [softwaremill/magnolia](https://github.com/softwaremill/magnolia)

![status](https://img.shields.io/github/issues/detail/state/softwaremill/magnolia/646)
- [#646](https://github.com/softwaremill/magnolia/issues/646) — SealedTrait.Subtype.typeAnnotations contains parent's paramTypeAnns instead of subtype's typeAnns
![status](https://img.shields.io/github/issues/detail/state/softwaremill/magnolia/647)
- [#647](https://github.com/softwaremill/magnolia/issues/647) — Monadic[Future].point uses Future(value) instead of Future.successful(value)

### [softwaremill/ox](https://github.com/softwaremill/ox)

![status](https://img.shields.io/github/issues/detail/state/softwaremill/ox/439)
- [#439](https://github.com/softwaremill/ox/issues/439) — Flow.range with a negative step emits only the first element

### [softwaremill/quicklens](https://github.com/softwaremill/quicklens)

![status](https://img.shields.io/github/issues/detail/state/softwaremill/quicklens/301)
- [#301](https://github.com/softwaremill/quicklens/issues/301) — Seq/Array atOrElse throws IndexOutOfBoundsException for missing indices instead of using default

### [softwaremill/sttp](https://github.com/softwaremill/sttp)

![status](https://img.shields.io/github/issues/detail/state/softwaremill/sttp/2880)
- [#2880](https://github.com/softwaremill/sttp/issues/2880) — Several `ByteBuffer.array()` calls don't check `hasArray()` and ignore position/limit
![status](https://img.shields.io/github/issues/detail/state/softwaremill/sttp/2881)
- [#2881](https://github.com/softwaremill/sttp/issues/2881) — toCurl drops multipart filename, content-type, and per-part headers
![status](https://img.shields.io/github/issues/detail/state/softwaremill/sttp/2882)
- [#2882](https://github.com/softwaremill/sttp/issues/2882) — DigestAuthenticator silently falls through to qop-unaware mode when server sends `qop="auth,auth-int"

### [softwaremill/sttp-ai](https://github.com/softwaremill/sttp-ai)

![status](https://img.shields.io/github/issues/detail/state/softwaremill/sttp-ai/470)
- [#470](https://github.com/softwaremill/sttp-ai/issues/470) — SnakePickle.snakeToCamel crashes on keys with leading, trailing, or consecutive underscores

### [softwaremill/tapir](https://github.com/softwaremill/tapir)

![status](https://img.shields.io/github/issues/detail/state/softwaremill/tapir/5219)
- [#5219](https://github.com/softwaremill/tapir/issues/5219) — Validator.show for Enumeration is missing the closing parenthesis
![status](https://img.shields.io/github/issues/detail/state/softwaremill/tapir/5220)
- [#5220](https://github.com/softwaremill/tapir/issues/5220) — SProductField overrides equals on (name, schema) without a matching hashCode
![status](https://img.shields.io/github/issues/detail/state/softwaremill/tapir/5221)
- [#5221](https://github.com/softwaremill/tapir/issues/5221) — Default CORS config does not allow PATCH
![status](https://img.shields.io/github/issues/detail/state/softwaremill/tapir/5222)
- [#5222](https://github.com/softwaremill/tapir/issues/5222) — [BUG] Multipart boundary uses scala.util.Random — predictable and not thread-safe

### [strymonas/strymonas-scala](https://github.com/strymonas/strymonas-scala)

![status](https://img.shields.io/github/issues/detail/state/strymonas/strymonas-scala/10)
- [#10](https://github.com/strymonas/strymonas-scala/issues/10) — int_div / long_div crash at staging time when both operands are statically zero
![status](https://img.shields.io/github/issues/detail/state/strymonas/strymonas-scala/11)
- [#11](https://github.com/strymonas/strymonas-scala/issues/11) — Cooked.collect returns elements in reverse stream order
![status](https://img.shields.io/github/issues/detail/state/strymonas/strymonas-scala/12)
- [#12](https://github.com/strymonas/strymonas-scala/issues/12) — goon_conj / goon_disj reorder operands in the (GExp, GRef) case, breaking short-circuit semantics

### [takapi327/ldbc](https://github.com/takapi327/ldbc)

![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/710)
- [#710](https://github.com/takapi327/ldbc/issues/710) — [Bug]: PooledDataSource.validateConnection uses handleError, dropping debug log effect
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/711)
- [#711](https://github.com/takapi327/ldbc/issues/711) — [Bug]: buildBatchQuery splits on case-sensitive "VALUES", breaks for lowercase "values"
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/712)
- [#712](https://github.com/takapi327/ldbc/issues/712) — [Bug]: Statement.execute throws MatchError for SHOW/DESCRIBE/EXPLAIN and other result-set queries
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/713)
- [#713](https://github.com/takapi327/ldbc/issues/713) — [Bug]: DataTypeParser.mediumblobType produces DataType.TINYBLOB() instead of MEDIUMBLOB()
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/714)
- [#714](https://github.com/takapi327/ldbc/issues/714) — [Bug]: ComStmtExecutePacket encoder uses uint24L for parameter types instead of uint16L (MySQL binary protocol violation)
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/715)
- [#715](https://github.com/takapi327/ldbc/issues/715) — [Bug]: SharedResultSet.isFirst returns true for any row past the first, not just row 1
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/716)
- [#716](https://github.com/takapi327/ldbc/issues/716) — [Bug]: Parameter.string SQL escaping is incomplete (missing NUL/CR/LF/Ctrl-Z/backspace) and orders quote-escape before backslash-escape
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/717)
- [#717](https://github.com/takapi327/ldbc/issues/717) — [Bug]: DataTypeParser.doubleType produces DataType.FLOAT (and DataType.DOUBLE doesn't exist in the model)
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/718)
- [#718](https://github.com/takapi327/ldbc/issues/718) — [Bug]: SSL.withTLSParameters drops fallbackOk, withFallback drops tlsParameters when chained
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/719)
- [#719](https://github.com/takapi327/ldbc/issues/719) — [Bug]: MysqlCharset.isOkayForVersion comparison is inverted (gb18030 rejected on MySQL 8.0)
![status](https://img.shields.io/github/issues/detail/state/takapi327/ldbc/720)
- [#720](https://github.com/takapi327/ldbc/issues/720) — [Bug]: VARCHAR rejects lengths > 255 at compile time (should allow up to 65535)

### [tarao/record4s](https://github.com/tarao/record4s)

![status](https://img.shields.io/github/issues/detail/state/tarao/record4s/169)
- [#169](https://github.com/tarao/record4s/issues/169) — record4s-circe encoder produces non-deterministic JSON field order
![status](https://img.shields.io/github/issues/detail/state/tarao/record4s/170)
- [#170](https://github.com/tarao/record4s/issues/170) — Selector.of[T] creates a Selector with empty labels — unapply returns EmptyTuple cast to ElemTypes

### [typelevel/fs2](https://github.com/typelevel/fs2)

![status](https://img.shields.io/github/issues/detail/state/typelevel/fs2/3725)
- [#3725](https://github.com/typelevel/fs2/issues/3725) — text.linesLimited lets through arbitrarily long lines when the line and its terminator land in the same chunk

### [typelevel/skunk](https://github.com/typelevel/skunk)

![status](https://img.shields.io/github/issues/detail/state/typelevel/skunk/1295)
- [#1295](https://github.com/typelevel/skunk/issues/1295) — timestamptz precision error message has typo "timestampz" (missing "t")

### [wvlet/wvlet](https://github.com/wvlet/wvlet)

![status](https://img.shields.io/github/issues/detail/state/wvlet/wvlet/1697)
- [#1697](https://github.com/wvlet/wvlet/issues/1697) — doubleQuoteIfNecessary doesn't escape internal double quotes, producing malformed SQL identifiers
![status](https://img.shields.io/github/issues/detail/state/wvlet/wvlet/1698)
- [#1698](https://github.com/wvlet/wvlet/issues/1698) — TripleQuoteString.sqlExpr drops embedded newlines from triple-quoted string literals
![status](https://img.shields.io/github/issues/detail/state/wvlet/wvlet/1699)
- [#1699](https://github.com/wvlet/wvlet/issues/1699) — DuckDBSchemaAnalyzer leaks JDBC Statement on every query

### [xebia-functional/Unwrapped](https://github.com/xebia-functional/Unwrapped)

![status](https://img.shields.io/github/issues/detail/state/xebia-functional/Unwrapped/136)
- [#136](https://github.com/xebia-functional/Unwrapped/issues/136) — zipWithIndex shares its counter across stream consumptions
![status](https://img.shields.io/github/issues/detail/state/xebia-functional/Unwrapped/137)
- [#137](https://github.com/xebia-functional/Unwrapped/issues/137) — PutPartiallyApplied.equals throws ClassCastException for non-matching types (forgot the canEqual check)

### [zio/zio](https://github.com/zio/zio)

![status](https://img.shields.io/github/issues/detail/state/zio/zio/10883)
- [#10883](https://github.com/zio/zio/issues/10883) — Schedule.dayOfMonth(30) crashes with DateTimeException in months that don't have day 30
![status](https://img.shields.io/github/issues/detail/state/zio/zio/10884)
- [#10884](https://github.com/zio/zio/issues/10884) — Queue.offerAll silently drops items when paired takers are already interrupted
![status](https://img.shields.io/github/issues/detail/state/zio/zio/10885)
- [#10885](https://github.com/zio/zio/issues/10885) — Queue.Sliding and Hub.Sliding can spin indefinitely when offer/publish keeps losing the race after slide

### [zio/zio-http](https://github.com/zio/zio-http)

![status](https://img.shields.io/github/issues/detail/state/zio/zio-http/4130)
- [#4130](https://github.com/zio/zio-http/issues/4130) — CORS middleware rejects actual cross-origin requests when method is not in allowedMethods
![status](https://img.shields.io/github/issues/detail/state/zio/zio-http/4131)
- [#4131](https://github.com/zio/zio-http/issues/4131) — ServerSentEvent.encoded silently turns newlines in eventType / id into spaces
![status](https://img.shields.io/github/issues/detail/state/zio/zio-http/4132)
- [#4132](https://github.com/zio/zio-http/issues/4132) — PathCodec.Annotated.equals is asymmetric and case class is missing a matching hashCode

### [zio/zio-json](https://github.com/zio/zio-json)

![status](https://img.shields.io/github/issues/detail/state/zio/zio-json/1600)
- [#1600](https://github.com/zio/zio-json/issues/1600) — Json.Obj.equals returns true for distinct objects with duplicate keys

### [zio/zio-protoquill](https://github.com/zio/zio-protoquill)

![status](https://img.shields.io/github/issues/detail/state/zio/zio-protoquill/747)
- [#747](https://github.com/zio/zio-protoquill/issues/747) — transaction commit/rollback wrapped in ZIO.succeed turns JDBC errors into unhandled defects
![status](https://img.shields.io/github/issues/detail/state/zio/zio-protoquill/748)
- [#748](https://github.com/zio/zio-protoquill/issues/748) — JdbcContext.probe leaks the JDBC Statement (never closed)
![status](https://img.shields.io/github/issues/detail/state/zio/zio-protoquill/749)
- [#749](https://github.com/zio/zio-protoquill/issues/749) — handleSingleResult silently swallows the multiple-row warning
![status](https://img.shields.io/github/issues/detail/state/zio/zio-protoquill/750)
- [#750](https://github.com/zio/zio-protoquill/issues/750) — String.startsWith / endsWith / contains compile to LIKE without escaping wildcards

### [zio/zio-schema](https://github.com/zio/zio-schema)

![status](https://img.shields.io/github/issues/detail/state/zio/zio-schema/1096)
- [#1096](https://github.com/zio/zio-schema/issues/1096) — dynamic: DynamicValue round-trip fails for Schema.Fallback (Left/Right/Both)
![status](https://img.shields.io/github/issues/detail/state/zio/zio-schema/1097)
- [#1097](https://github.com/zio/zio-schema/issues/1097) — dynamic: DynamicValue round-trip fails for Schema.NonEmptySequence and Schema.NonEmptyMap
![status](https://img.shields.io/github/issues/detail/state/zio/zio-schema/1098)
- [#1098](https://github.com/zio/zio-schema/issues/1098) — Patch.Temporal for ZonedDateTimeType casts to LocalDate (ClassCastException)
![status](https://img.shields.io/github/issues/detail/state/zio/zio-schema/1099)
- [#1099](https://github.com/zio/zio-schema/issues/1099) — SchemaEquality compares rTuple.right with itself instead of lTuple.right
![status](https://img.shields.io/github/issues/detail/state/zio/zio-schema/1100)
- [#1100](https://github.com/zio/zio-schema/issues/1100) — MessagePack decoder: enum boundary check is off by one (ArrayIndexOutOfBoundsException for caseIndex == cases.length)
![status](https://img.shields.io/github/issues/detail/state/zio/zio-schema/1101)
- [#1101](https://github.com/zio/zio-schema/issues/1101) — MessagePack Fallback decoder uses path label "either" in error, and the size error says "1 or 2" instead of "2 or 3"
![status](https://img.shields.io/github/issues/detail/state/zio/zio-schema/1102)
- [#1102](https://github.com/zio/zio-schema/issues/1102) — Avro codec encodes ByteType as bare INT without a discriminator, so Schema[Byte] becomes Schema[Int] after roundtrip


## How this was built

The pipeline lives in a separate working directory (94 cloned Scala projects, ~10K-iteration loop). Each candidate bug:

1. Found via static analysis or fuzzing
2. Reduced to a minimal `scala-cli` reproducer
3. Verified to compile + reproduce on Scala 3.8.3 with the latest published library version
4. Cross-checked against the project's existing issues (no duplicate filing)
5. Manually reviewed before submission

The full pipeline (`ralph-loop`, prompts, heuristics, reproducers) is private for now.

If your project doesn't accept AI-assisted issue reports, please let me know — and ideally publish a rule the way Eugene Yokota did for sbt 2.0, so contributors know up front.
