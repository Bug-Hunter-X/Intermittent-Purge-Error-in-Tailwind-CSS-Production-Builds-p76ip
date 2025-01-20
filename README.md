# Intermittent Purge Error in Tailwind CSS Production Builds

This repository demonstrates a bug related to Tailwind CSS's purge functionality.  The issue causes some styles to be removed during production builds, seemingly randomly depending on the order of class names. This only happens in production; development builds are unaffected.

## Bug Description
The bug manifests as missing styles in the production build of a project. This is inconsistent, meaning the same classes used in different orders might have different effects.  We suspect the order of class names in the source code may be influencing the purge process unexpectedly.

## How to Reproduce
1. Clone the repository.
2. Run `npm install`.
3. Run `npm run build` (for the buggy production build)
4. Observe the missing styles in the generated CSS.
5. Compare it to the `npm run dev` result, where the styles are applied properly.

## Solution
The solution involves explicitly specifying the classes in the purge configuration.

## Additional Notes
The problem is likely due to an interaction between the order of CSS classes and Tailwind's purge algorithm.  This example illustrates a scenario, but the exact nature of the interaction might be subtle and depend on other project specifics.