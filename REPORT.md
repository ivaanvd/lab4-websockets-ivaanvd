# Lab 4 WebSockets ELIZA — Project Report

## Description of Changes
- Completed the missing logic in `ElizaServerTest.kt`, focusing on the `onChat()` test.
- Implemented the test setup using `ComplexClient`, `CountDownLatch`, and assertions.
- Verified that at least four messages are received from the server.
- Checked that one of the responses matches `"We were discussing you, not me."`.
  - Why `size = list.size` is necessary (to capture message count before assertions).
  - Why `assertEquals` cannot be used (as WebSocket messages are asynchronous and timing may vary).
  - Why an interval check (`assertTrue`) is more reliable for asynchronous tests.
- In `ComplexClient`, completed the condition to send `"you"` after the third received message to trigger a server response.
- Verified that both `onOpen()` and `onChat()` tests run successfully with `./gradlew test`.

## Technical Decisions
- Used **Spring Boot WebSockets** and **JUnit 5** for integration testing.
- Applied `CountDownLatch` to synchronize message flow between client and server.
- Replaced exact value assertions with range checks due to asynchronous behavior.
- Followed the structure of the `onOpen()` test for consistent testing style.
- Ensured code formatting with **Ktlint** (`./gradlew ktlintFormat`).

## Learning Outcomes
- Learned how to test asynchronous WebSocket communication in Kotlin.
- Understood the importance of synchronization and timing control in WebSocket tests.
- Practiced using assertions that adapt to non-deterministic message timing.
- Improved understanding of client-server message exchange in WebSocket protocols.

## AI Disclosure
### AI Tools Used
- ChatGPT

### AI-Assisted Work
- Used only for writing this `REPORT.md` and minor clarifications on WebSocket testing.
- No AI-generated code was included in the test implementation.

### Original Work
- All test logic and WebSocket interaction code were implemented manually.
- Verified and debugged the behavior using local runs and manual inspection.
