https://hp-jira.external.hp.com/browse/HPXAPPS-53072

---
### To Do
1. Remover timers e justar loading state com a exibição dos skeletons
2. Atenção com a props de loading do componente deviceList 
3. Trocar skeleton implementado por componente ui-tk com props loading

#### Upgrade 
Ui-toolkit 3.113.10

## DEBITOS TECNICOS A SEREM COBERTOS
### Loading State Coordination

**Severity:** HIGH | **Priority:** HIGH

#### Problem Statement

Multiple independent loading states tracked without coordination, leading to endless spinners, race conditions, and poor user experience.

#### Evidence

- **JIRA Tickets:**
    
    - HPXAPPS-48979: Device list not loading intermittently
    - HPXAPPS-43739: Endless spinner (guest mode)
    - HPXAPPS-43594: Endless spinner (sign-in)
    - HPXAPPS-43429: Infinite loading on mobile
    - HPXAPPS-42863: Incorrect navigation from totalCount
- **Current Loading Sources:**
    
    - Feature flags (4+ different flags)
    - GraphQL device data
    - PaaS digital services
    - Auth state transitions
    - Navigation processing
    - Image API (per device)
    - Platform detection

#### Impact

- **User-Facing:** Most frustrating UX issues (endless spinners, blank screens)
- **Support Burden:** Highest ticket volume
- **Diagnostic Difficulty:** Intermittent, hard to reproduce

#### Fix Strategy

**Phase 1: Design**

- Design loading state machine with explicit states
- Define critical vs secondary loading
- Establish timeout strategies per loading type
- Create loading state visualization

**Phase 2: Implementation**

- Create `useLoadingStateMachine` hook
- Implement coordinatedLoading reducer
- Add timeout guards (10s critical, 30s secondary)
- Build `LoadingStateProvider` context

**Phase 3: Integration**

- Migrate App.tsx to use state machine
- Update DevicesProvider coordination
- Add loading state debugging tools
- User feedback for loading stages

#### Solution Architecture

```
INITIALIZING  └─> LOADING_CRITICAL (Feature flags, Auth) [10s timeout]        └─> LOADING_PRIMARY (Device data) [15s timeout]              └─> LOADING_SECONDARY (Images, PaaS) [30s timeout]                    └─> READY
```

#### Acceptance Criteria

- [ ]  Single source of truth for loading state
- [ ]  No loading state can hang indefinitely (max 30s)
- [ ]  User sees specific loading feedback
- [ ]  95%+ uptime for device list page
- [ ]  Zero endless spinner incidents

### Device Data Synchronization

**Severity:** MEDIUM | **Priority:** MEDIUM

#### Problem Statement

Inconsistent device data across multiple sources (GraphQL, NBAPI, PaaS) causing incorrect device counts and stale data.

#### Evidence

- **JIRA Tickets:**
    - HPXAPPS-47572: Cloud devices showing when logged out
    - HPXAPPS-42863: totalCount mismatch
    - HPXAPPS-42465: Missing totalCount
    - HPXAPPS-48012: Devices blocked by PaaS

#### Fix Strategy

**Phase 1: Single Source Refactor**

- Design unified device data layer
- 
- Create `useUnifiedDeviceData` hook
- Implement cache coordination strategy
- Add data validation layer

**Phase 2: GraphQL Primary**

- Make GraphQL the single source of truth
- Add fallback mechanisms for offline
- Implement optimistic updates
- Add data consistency tests

#### Acceptance Criteria

- [ ]  Single source of truth for device data
- [ ]  totalCount always matches displayed devices
- [ ]  Zero stale data issues
- [ ]  GraphQL-first with NBAPI fallback


---
Scope: 

- Refactor components **to control** their own fetch + loading boundary, including:
    - Device List Content
    - Device Status Widget (already progressive)
    - Device Image (with local fallback)
- Each section should expose states:
    - loading, ready, empty.
- Create or adjust skeletons per component, maintaining fixed sizes to avoid layout shift.
- Add logs to register the loading times:
    - `time_to_first_section_visible`
    - `time_to_sections_visible`
    - `time_to_full_view_ready`
- Remove global loading spinner.
- Ensure that parallel queries for shared data do not generate duplicate calls.

### Feature Flags
- DeviceMFEFeatureFlags.NAVIGATION_STRATEGY
- DeviceMFEFeatureFlags.DEVICE_LIST -> aparece ou não os devices
- DeviceMFEFeatureFlags.DEVICES_X_FORYOULINK
- DeviceMFEFeatureFlags.TRACKING_CARD
- DeviceMFEFeatureFlags.FIRST_DEVICE_CARD
- DeviceMFEFeatureFlags.DEVICE_STATUS@pa
- DeviceMFEFeatureFlags.DEVICES_X_POPULAR_FEATURES
