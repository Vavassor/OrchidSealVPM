# Orchid Seal VPM Package Listing

Listing for Orchid Seal's packages in VRChat Package Manager. (VPM)

## 📃 Rebuilding the Listing

Whenever you make a change to the `main` branch, or when you trigger it manually, the 'Build Repo Listing' action will make a new index of all the releases available and publish them as a website hosted fore free on GitHub Pages. This listing can be used by the VPM to keep your package up to date, and the generated index page can serve as a simple landing page with info for your package. The URL for your package will be in the format https://username.github.io/repo-name.

## 🏠 Customizing the Landing Page

The contents of the `Website` directory can be customized to change the appearance of the landing page. Most of the information will be automatically filled in with information from [`source.json`](source.json). Customizing the landing page by hand is not required.

## Build Listing
[build-listing.yml](.github/workflows/build-listing.yml)

This is a composite action which builds a vpm-compatible [Repo Listing](https://vcc.docs.vrchat.com/vpm/repos) based on the items you've added to your `source.json` file. you've created. In order to find all your releases and combine them into a listing, it checks out [another repository](https://github.com/vrchat-community/package-list-action) which has a [Nuke](https://nuke.build/) project which includes the VPM core lib to have access to its types and methods. This project will be expanded to include more functionality in the future - for now, the action just calls its `BuildRepoListing` target, which calls `RebuildHomePage` when it completes. If you wanted to make an action that just rebuilds the home page, you could call that directly instead - just copy the existing call and replace the target names.
