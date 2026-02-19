# FlowKit KMP

**FlowKit** is a Kotlin Multiplatform SDK that allows mobile apps to embed structured decision flows such as onboarding, questionnaires and assessments without building a custom evaluation engine.

The SDK provides a reusable mobile flow engine that works on **Android and iOS** while allowing full control over the UI so the experience matches your app's design system.

---

## Why FlowKit exists

Most mobile apps eventually need to:

* onboard users with multi-step flows
* collect structured information
* evaluate knowledge or profile a user
* enable or disable features based on answers
* run eligibility or configuration flows

Teams usually implement this logic from scratch.
The complexity is not the screens — it's:

* navigation logic
* conditional branching (skip logic)
* scoring
* partial progress persistence
* resuming sessions
* edge cases

FlowKit solves that.

---

## What FlowKit is (and is not)

FlowKit **is:**

* a mobile decision flow engine
* an assessment and onboarding framework
* embeddable inside existing apps
* UI-agnostic

FlowKit **is NOT:**

* a form builder website
* a survey SaaS
* a backend service
* a screen generator

---

## Core Concept

FlowKit separates **logic** from **presentation**.

The engine manages the flow.
Your app renders the UI.

The SDK emits renderable state:

```
QuestionState
OnboardingStepState
ResultState
```

Your UI (or our default UI) displays it.

---

## Integration Modes

### 1) Plug & Play UI

Use the provided screens:

```kotlin
FlowKitQuestionnaireScreen(session)
```

---

### 2) Theming

Match your brand:

* colors
* typography
* shapes
* spacing

---

### 3) Fully Custom UI

Implement your own UI while using the engine:

```kotlin
@Composable
fun CorporateQuestionScreen(
    state: QuestionState,
    actions: QuestionActions
)
```

This allows companies with strict design systems (banks, fintech, enterprise apps) to integrate FlowKit without changing their visual identity.

---

## Supported Flows

* onboarding flows
* questionnaires
* assessments
* profile classification
* feature gating
* eligibility checks

---

## Flow Definition

Flows are defined via JSON configuration.

Example:

```json
{
  "id": "risk_profile",
  "steps": [
    {
      "type": "single_choice",
      "id": "q1",
      "title": "How familiar are you with investments?",
      "options": ["None", "Basic", "Advanced"]
    }
  ]
}
```

---

## Platforms

* Android (Jetpack Compose)
* iOS (SwiftUI via Kotlin Multiplatform)

---

## Modules

* flowkit-compose → default Android UI
* flowkit-swiftui → default iOS UI
* samples → demo applications

---

## License

FlowKit UI and integration modules are open-source.
The core engine is distributed as a binary dependency under a commercial license.

Contact: (you will add later)

---

## Status

Early development.
The goal is to validate real production integrations.

If you are interested in trying FlowKit in your app, open an issue or discussion.

---

## Roadmap

* [ ] Core flow sessions
* [ ] Conditional branching
* [ ] Assessment scoring
* [ ] Resume progress
* [ ] Custom UI contract validation
* [ ] Flow builder tool