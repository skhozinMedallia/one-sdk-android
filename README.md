**PR Title Format**: `<JIRA-ID> - <TEST-ID> - <Summary>`

### 📝 Summary
- **Context**: *(Purpose of this PR)*
- **Approach**: *(Technical implementation details)*
- **Risk Level**: *(Low / Medium / High)*

### 🔗 Linked Work
**Jira & Zephyr**
- [ ] iOS: [MDMS-XXXXX](Link)
- [ ] Android: [MDMS-XXXXX](Link)
- [ ] Test Case: [MDMS-TXXXXX](Link)

**Related DQE Tickets**
- [ ] iOS: [DQE-XXXXX](Link)
- [ ] Android: [DQE-XXXXX](Link)

### ⚙️ Backend & API Impact
- **State Changes**: *(API calls, config flags, or property changes)*
- **Validation**: *(Verification steps for backend changes)*
- **Cleanup Strategy**: *(How state is reverted in the automation lifecycle)*

### ℹ️ Results & Evidence
**Jenkins Job Links**
- [ ] iOS: [Result Link](Link)
- [ ] Android: [Result Link](Link)

**Execution Details**
- **Environment**: *(e.g., `digital-colo-qa`)*
- **Property**: *(iOS / Android / Web)*
- **Branch**: `MDMS-XXXXXSDK`
- **Visuals**: *(Screenshots of PASSED Jenkins Jobs)*

---

### ✔️ Author Self-Checklist
*Author: Please verify these quality standards before requesting a review.*
- [ ] **State Cleanup**: All API/Property changes are reverted in `afterAll` or `afterEach`.
- [ ] **Logic Separation**: No assertions or raw driver calls (`argusBrowser`) in test files.
- [ ] **Stability**: No `waitMs()` used; explicit waits only.
- [ ] **JSDoc**: All public methods have `@summary`, `@param`, and `@returns`.
- [ ] **Clean Code**: Removed commented-out code and unused variables.
- [ ] **Method Reuse**: Confirmed no existing method could be refactored to handle this (no duplicates).
- [ ] **PR Status**: Applied an appropriate PR status label (WIP, Ready for Review, etc.).
- [ ] **Assignee**: Assigned a responsible reviewer to the PR.

---

### 🔍 First-Reviewer Checklist
*Reviewer: Please verify these technical requirements before approving/passing to the next stage.*
- [ ] **Test-Level Assertions**: No assertions in the test file (all moved to POM).
- [ ] **Method Reuse**: Verified this change is unique and does not duplicate existing helpers.
- [ ] **Naming**: `@summary` matches logic; platform terms (`bundleId` vs `packageName`) are correct.
- [ ] **Cleanup Integrity**: Cleanup uses specific IDs rather than global `deleteAll` commands.
- [ ] **Explicit Waits**: Confirmed no arbitrary sleeps or `waitMs` are hidden in helpers.
- [ ] **Locators**: Avoided brittle CSS; ensured `data-aut` or `accessibility-id` usage.
- [ ] **Cross-Project Impact**: Verified that Web/Config changes do not break the existing functionality.
- [ ] **Evidence**: Provided links/screenshots confirm the specific tests passed in the correct environment.
