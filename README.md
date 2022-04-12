# Code Repository Development Policy Stages

A definition of the requirements that need to be satisfied
for our code repositories to meet various levels of _development stages_
designed to indicate the 'product worthiness' of the code they contain.

It is natual for all code to start as an early implementation of a
design or concept. Initial implementations are often prototypes or
proof of concepts where features appear and disappear quickly where
development practices are often deliberately relaxed.

At some stage in the code's lifetime it becomes _valuable_ and the desire
to control its behaviour becomes as important (or more important)
that enhancing it. As code repository development practices evolve and
vary considerably, often based on the programming language, we wanted to define
a set of rules that could be used to classify each of our repositories
using a set of rules that we consider indicate the repository's
_product worthiness_.

That's what this document is about - identifying a small number of "stages"
that a repository is expected to pass through on it's journey from
_prototype to product_.

# 1.0.0-alpha.1

**DOCUMENT UNDER REVIEW**

The stages defined here help viewers and contributors understand what is
needed from them if they contribute to the code and also how they can expect
the code to be built, published and deployed. Once the user understands the
stage they should be able to understand how to use the repository.

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
- The repository **MUST** document a branch policy
- Software releases **MUST** be supported, using semantic versioning
  to tag each release 
- The repository **SHOULD** declare a code style guide
- The repository **SHOULD** contain [Unit tests]

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
- The repository **MUST** contain a CHANGELOG that is constructed automatically
  from the content of commit messages. If you use [Commitizen] as a tool
  to generate the CHANGELOG our [.cz.yaml] configuration file will be of value -
  it recognizes the commit message types and structures the CHANGELOG sections
- The CHANGELOG content **MUST** contain details of every commit, regardless of
  whether the change alters the code's behaviour. For example, documentation
  and test changes must be present in the CHANGELOG file.
- The CI/CD process **SHOULD** contain some [Functional tests] where appropriate

>   **Summary**: The highest level of policy. Commit messages and code style
    conform to a standard, and are enforced automatically. Code is built
    and can be deployed automatically. Users will clearly understand what is built,
    how it's built, how it's delivered, and what changes have been made

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
- Commitizen [.cz.yaml] configuration

---

[.cz.yaml]: https://gist.github.com/alanbchristie/19077203307101e9e9d52086488d4921
[commitizen]: https://pypi.org/project/commitizen
[conventional commit style guide]: https://discourse.squonk.it/t/conventional-commit-style-guide
[functional tests]: https://en.wikipedia.org/wiki/Functional_testing
[pre-commit]: https://pre-commit.com
[rfc 2119]: https://www.ietf.org/rfc/rfc2119.txt
[unit tests]: https://en.wikipedia.org/wiki/Unit_testing
