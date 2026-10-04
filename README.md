# Circle Chain

A creature made of circles and basic maths. The first circle follows your mouse, every other circle follows the one in front. Change the settings and it becomes a fish, snake, caterpillar or whip. Eat the food to grow.

**Play:** visit https://maths-of-circles.netlify.app/.

## The maths

- **Follow rule:** each circle keeps a fixed distance `d` from the one ahead, in its current direction:
  `pᵢ = pᵢ₋₁ + d · (pᵢ − pᵢ₋₁) / |pᵢ − pᵢ₋₁|`
- **Spacing:** `d = k · (rᵢ₋₁ + rᵢ)`. At `k = 1` circles touch, below 1 they merge into a body.
- **Radius shapes** (`t = i/(n−1)`):
  - Linear: `r₀(1 + g·t)`
  - Geometric: `r₀(1 + g)ᵗ`
  - Fish: `r₀·sin(π(0.1 + 0.9t)^0.7)`
- **Outline:** heading `θ = atan2(Δy, Δx)`, normal `(−sin θ, cos θ)`, edge points `pᵢ ± rᵢ·normal`, smoothed with Bézier curves.
- **Swimming:** the head is pushed sideways by `sin(5t)`, and the wave travels down the body.
- **Eating:** food is eaten when the distance to the head is less than `r₀ + r_food`.

## Controls

Circles `n`, base radius `r₀`, spacing `k`, growth `g`, radius profile, wiggle, colour. Presets: Fish, Snake, Caterpillar, Whip, Tadpole. Turn on **Skeleton** to see the maths drawn live.
