---
title: "Post title goes here"
description: "One sentence shown under the title on the section page and in link previews."
# tags: [dp, graphs]      # optional, shown in the post header
# math: false             # optional, MathJax loads on every post unless you turn it off
---

<!--
  HOW TO PUBLISH
  1. Copy this file to _posts/<section>/YYYY-MM-DD-short-slug.md
     where <section> is icpc, papers, or research. The folder decides which
     section page lists the post. No category line is needed in the front matter.
  2. The URL becomes /<section>/short-slug/ and the post appears on the
     section page and under "Writing" on the home page on the next push.
  Drafts in this folder are never published. Preview them locally with
  `bundle exec jekyll serve --drafts`.
-->

Open with the one thing a reader should take away. Keep the first paragraph short.

## Headings start at level two

Level one is the post title. Use `##` for sections and `###` for subsections.

Inline math uses double dollar signs on both sides, like $$O(n \log n)$$ or
$$\mathbb{E}[T_n]$$. Single dollar signs are left alone so prices and shell
variables do not turn into math. Display math goes on its own lines:

$$
\mathbb{E}[T_n] = \sum_{k=1}^{n} \frac{1}{p_k}
$$

Code blocks name the language after the opening fence:

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n; cin >> n;
    vector<long long> dp(n + 1, 0);
    dp[0] = 1;
    for (int i = 1; i <= n; i++) dp[i] = dp[i - 1] * 2 % 1'000'000'007;
    cout << dp[n] << '\n';
}
```

> A blockquote works well for the key takeaway or a quote from the paper.

| Model     | Accuracy | ERD |
|-----------|---------:|----:|
| ViT       |     81.2 | 7.4 |
| ConvFormer|     82.0 | 3.1 |

Images live in `assets/img/` and are referenced with a site-root path:

```markdown
![What the figure shows](/assets/img/example.png)
```
