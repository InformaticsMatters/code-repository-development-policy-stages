# Code Repository Development Policy Stages 1.0.0-alpha.1

A definition of the requirements that need to be satisfied
for code repositories we to meet specific _development stages_. Code
naturally passes through conceptual and prototype stages where development
practices are often more relaxed before entering a more mature 'production
quality' stage usually associated with the delivering and maintenance
of the code artefacts.

The stages defined here help viewers and contributors understand what is
needed from them if they contribute to the code and also how they can expect
the code to be built, published and deployed. Once the user understand the
stage they should be able to understand how to use the repsository.

We have defined four policy stages, numbered 0 to 3. The higher the
stage number, the more demanding the policy.

>  The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”,
    “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to
    be interpreted as described in [RFC 2119].

## Policy Stage 0
Repositories at **Stage 0** are the weakest in terms of policies. They
are repositories that represent legacy code that would be expensive to or
offer very little value in migrating to a higher policy or are early
representations of code, expected to migrate to higher stages as their features
evolve. For agility the policy demands on Stage 0 are deliberately weak.

1. The repository **SHOULD** have a README file in the root of the repository
2. The repository **SHOULD** display our "Policy Stage: 0" badge
   in the repo's natural root README file

>   **Summary**: In order to understand how to contribute to or use a "Stage 0"
    repository you are likely to need to talk to the author

Use the badge in your project's README.md:
```md
[![Policy Stage: 0](https://img.shields.io/badge/Policy%20Stage-&#9734;&#9734;&#9734;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-policy-stages)
```

Using the badge in README.rst:
```doctest
.. image:: https://img.shields.io/badge/Policy%20Stage-&#9734;&#9734;&#9734;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-policy-stages

```

Which looks like this:
![Policy Stage: 0](https://img.shields.io/badge/Policy%20Stage-&#9734;&#9734;&#9734;-dc332e)

> Repositories that have no badge SHOULD be considered "Policy Stage 0" repositories.

## Policy Stage 1
1. Repository **MUST** adopt our Conventional Commit message policy
2. Automated validation of the commit message MUST be implemented.
   This will normally be achieved using git's pre-commit hooks typically 
   automatically configured using [pre-commit] and its corresponding
   `.pre-commit-config.yaml` file, that will be found in the repository root
3. The repository **MUST** have a README file in the root of the repository
4. The repository **MUST** clearly identify the repository build artefacts,
   i.e. how the code manifests itself (i.e. as a container image)
   and instructions for building and publishing them
5  The repository **MUST** display our "Policy Stage: 1" badge
   in the repo's natural root README file

>   **Summary**: Commit messages conform to a standard, are enforced automatically,
    and it will be clear what the repository's artefacts are and how to build them  

Use the badge in your project's README.md:
```md
[![Policy Stage: 1](https://img.shields.io/badge/Policy%20Stage-&#9733;&#9734;&#9734;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-policy-stages)
```

Using the badge in README.rst:
```doctest
.. image:: https://img.shields.io/badge/Policy%20Stage-&#9733;&#9734;&#9734;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-policy-stages

```

Which looks like this:
![Policy Stage: 0](https://img.shields.io/badge/Policy%20Stage-&#9733;&#9734;&#9734;-dc332e)

## Policy Stage 2
- The repository **MUST** satisfy all the policies defined in "Stage 1"
- The repository **MUST** employ CI/CD to build and publish the repo's artefacts
  For GitHub this will be the use of _Actions_ located in the repository's
  `.github/workflows` directory. For GitLab this will be the use
  of a `github-ci.yml` script
- The repository **MUST** document a branch and tag policy
- The repository **SHOULD** declare a code style guide
- The repository **SHOULD** contain unit tests

>   **Summary**: Commit messages conform to a standard, are enforced automatically,
    repository artefacts are built automatically and a development (branch and tag)
    policy will be clear

Use the badge in your project's README.md:
```md
[![Policy Stage: 1](https://img.shields.io/badge/Policy%20Stage-&#9733;&#9733;&#9734;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-policy-stages)
```

Using the badge in README.rst:
```doctest
.. image:: https://img.shields.io/badge/Policy%20Stage-&#9733;&#9733;&#9734;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-policy-stages

```

Which looks like this:
![Policy Stage: 0](https://img.shields.io/badge/Policy%20Stage-&#9733;&#9733;&#9734;-dc332e)

## Policy Stage 3
- The repository **MUST** satisfy all the policies defined in "Stage 3"
- The repository **MUST** declare a code style guide
- The repository **MUST** contain unit tests and publish code coverage figures
- [Pre-commit] (client-side) static analysis (code linting and style enforcement)
  **MUST** be enforced
- The CI/CD process **MUST** run Unit tests
- The repository **MUST** contain clear instruction on how to use the artefacts
  i.e. it must have a guide for deploying and using the artefacts
- The repository **MUST** employ a continuous delivery mechanism that
  is documented and able to deploy to a multiple sites (typically at least
  a staging and production site)
- The CI/CD process **SHOULD** contain enhanced Functional testing where appropriate

>   **Summary**: The highest level of policy. Commit messages and code style
    conform to a standard, and are enforced automatically. Code is built
    and can be deployed automatically. Users will clearly understand what is built,
    how it's built and how it's delivered

Use the badge in your project's README.md:
```md
[![Policy Stage: 1](https://img.shields.io/badge/Policy%20Stage-&#9733;&#9733;&#9733;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-policy-stages)
```

Using the badge in README.rst:
```doctest
.. image:: https://img.shields.io/badge/Policy%20Stage-&#9733;&#9733;&#9733;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-policy-stages

```

Which looks like this:
![Policy Stage: 0](https://img.shields.io/badge/Policy%20Stage-&#9733;&#9733;&#9733;-dc332e)

## References

- Our [Conventional Commit style guide]

---

[conventional commit style guide]: https://discourse.squonk.it/t/conventional-commit-style-guide
[pre-commit]: https://pre-commit.com
[rfc 2119]: https://www.ietf.org/rfc/rfc2119.txt
