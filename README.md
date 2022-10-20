
# dotnet formatting example

In this project i have added different mechanisms to enforce good formatting

In the main branch I have added the following mechanisms so enforce good formatting:
- an .editorconfig file copied from the dotnet format repo with style preferences
- A commit hook with [Husky.Net](https://github.com/alirezanet/husky.net) that runs dotnet format on each commit
- A Github action that runs on each pull request and prevents merging if the formatting is not good running dotnet format --verify-no-changes

If you go for this approach you should tell all developers to enable code cleanup on save in their editor

in [this PR](https://github.com/petteas/dotnetformattingexample/pull/5) i have added badly formatted code and it shows the check failing

in [this PR](https://github.com/petteas/dotnetformattingexample/pull/6) I have added [CSharpier](https://github.com/belav/csharpier) to the mix. I have done the following:
- Removed Whitespace-related stuff from the editor config file
- Made CSharpier run together with the analyzer part of dotnet format in both commit hook and Github action

If you go for this approach you should tell all developers to install CSharpier-extension and enable it on save in their editors

I like the later approach best because CSharpier is way more opinionated than dotnet format. And formatting should be opinionated and give few possibilities to change the structure
