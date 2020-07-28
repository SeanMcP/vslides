# Side Panel

> A brief origin story

For a feature, Alpha wanted a component that would:

- Slide out from the side on desktop
- Position itself relative to the header
- Slide up from the bottom on mobile
- Conditionally overlay
- Animate in transition
- Be reusable

<!--








-->

## Attempt 1: Use `@reach/dialog`

I'm already familiar with this library and it seemed like a good use case. But:

- Still another dependency
- Could not handle conditional overlay 😭

<!--








-->

## Attempt 2: Just make it work

> "'Well done is better than well said' – Ben Franklin'" – Shawn Rancatore

The working component was a mess of state management and timeouts

Checked all the boxes, except reusability ❌

<!--








-->

## Attempt 3: A higher-order component

Abstracted all the logic into a HOC that could wrap any component

<!-- A hooks only work for functional components -->

Looked fancy (backpats) but:

- State changes caused the wrapped component to re-render
- Animated transition weren't possible 🧊

<!--








-->

## Attempt 4: Rethinking the API

What we really want a component that:

- Handles the transition state
- Knows when to render
- Just works ✨

[🧪 Experimenting with state delays](https://codesandbox.io/s/delayed-state-changes-zudg4)

<!--








-->

## Final result

`SidePanel` that needs:

- `isOpen: boolean` prop
- children to render

Handles the rest under the hood

[🦮 Guided tour of `SidePanel`](https://github.com/nicheinc/Website/blob/feature/account-pane/app/components/common/SidePanel.tsx)

<!--








-->

## Conclusion

### Component

- New React features _can_ make interactive logic easier
- Should probably rename the component `Panel`

### Process

- The first option is not always the best
- Getting it to work is a good place to start
