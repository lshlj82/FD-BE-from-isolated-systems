# Fermions and bosons on an evenly spaced ladder

An interactive web page on small Fermi and Bose systems with evenly spaced, nondegenerate energy levels. With levels spaced like this, every microstate of either system is a partition of an integer. Counting and averaging these microstates is enough to see the Fermi–Dirac and Bose–Einstein distributions emerge.

The page is supplementary material for the Statistical Physics 2 lecture on quantum statistics, and is meant to join the [Statistical Physics 2 interactive demos](https://lshlj82.github.io/statphys2-GNU/) ([source](https://github.com/lshlj82/statphys2-GNU)), as demo 4+ after [Boson vs Fermion](https://lshlj82.github.io/boson-vs-fermion/).

**Live page:** https://lshlj82.github.io/FD-BE-from-isolated-systems/ (Korean: https://lshlj82.github.io/FD-BE-from-isolated-systems/ko.html) It follows Problems 7.16 and 7.17 of D. V. Schroeder's *An Introduction to Thermal Physics* and the article by Arnaud *et al.* on which they are based. It is available in English (`index.html`) and Korean (`ko.html`), and each page links to the other.

## What's on the page

- **Microstate explorer.** For $`q = 0`$ to $`12`$ energy units, all microstates are drawn side by side: fermions as dot diagrams and bosons as occupation numbers. Hovering over a column shows the partition it represents and highlights the same partition in both diagrams. The exact occupancies are listed as fractions.
- **Fitting the occupancies.** The exact occupancies are fitted with the Fermi–Dirac and Bose–Einstein distributions by unweighted least squares (Nelder–Mead), and sliders let you test your own $`\mu`$ and $`T`$ against the best fit. For $`q = 6`$ the best fits are:
  - fermions: $`\mu = 0.50\,\epsilon`$ above the top level filled at $`q = 0`$, and $`k_BT = 2.25\,\epsilon`$;
  - bosons: $`\mu = -0.04\,\epsilon`$ and $`k_BT = 2.28\,\epsilon`$.

  A short SciPy `curve_fit` example reproduces these numbers.
- **Entropy and temperature.** The page plots $`S/k_B = \ln p(q)`$, which is the same for fermions and bosons, together with the Hardy–Ramanujan approximation. It compares temperature estimates at the chosen $`q`$: from the two fits, from backward and central slopes, from the thermodynamic limit $`k_BT \approx \sqrt{6q}\,\epsilon/\pi`$, and from the canonical and grand canonical ensembles with the same average energy.
- **Isolated, canonical, and grand canonical.** Fermion occupancies in the three ensembles are compared on a linear or log scale, using the exact series of Arnaud *et al.*
- **Remarks.** The page closes with the fermion–boson correspondence (particle–hole conjugation and transposed partitions), the tails of the Fermi–Dirac distribution in small systems, and the linear heat capacity.

## Usage

Each language version is a single self-contained HTML file with no build step. Open it in a modern browser, or serve the folder with GitHub Pages (**Settings → Pages → Deploy from a branch**, root folder).

The page loads two things from the network:

- [MathJax 3.2.2](https://www.mathjax.org/) from cdnjs, for equations;
- fonts from Google Fonts: Source Serif 4, IBM Plex Sans, IBM Plex Mono, IBM Plex Sans KR, and Noto Serif KR. Without a connection it falls back to system fonts.

Partitions, fits, and ensemble sums are computed in plain JavaScript, and plots are drawn as SVG. The light/dark button uses the same stored setting (`netsci-theme`) as the other course demos.

## 한국어 안내

등간격 에너지 준위를 가진 작은 페르미 계와 보스 계를 다루는 통계물리 2 인터랙티브 보충 자료입니다. 한국어 페이지는 `ko.html`입니다. 주요 내용은 다음과 같습니다.

- 미시 상태 탐색기: 정수 분할로 나타낸 페르미온과 보손의 미시 상태
- 페르미–디랙 분포와 보스–아인슈타인 분포로 점유수 맞춤하기 (SciPy 예제 포함)
- 엔트로피 $`\ln p(q)`$와 여러 가지 온도 추정값의 비교
- 고립계, 정준 앙상블, 대정준 앙상블의 비교

이 페이지는 Claude Opus 5.5(Anthropic)가 제작했습니다.

## Credits

The page, its explanations, numerical results, and interactive figures were created by **Claude Opus 5.5** (Anthropic) and should be read alongside the sources below.

## References

1. D. V. Schroeder, *An Introduction to Thermal Physics* (Addison-Wesley, 2000), Problems 7.16 and 7.17.
2. J. Arnaud, J. M. Boé, L. Chusseau, and F. Philippe, "Illustration of the Fermi–Dirac statistics," *American Journal of Physics* **67**, 215–221 (1999).
3. K. Schönhammer and V. Meden, "Fermion–boson transmutation and comparison of statistical ensembles in one dimension," *American Journal of Physics* **64**, 1168–1176 (1996), as cited in Ref. 2.
