# Code Repository Development Stages

A set of stylistic rules used to classify our software repositories
into one of a number of _development stages_. The rules are structured
to create a number of _numerical stages_ that we consider represent traits of
software repositories that exhibit a pattern of _increasing 'product quality'_.

**Background**

We have a lot of software repositories and need to _guide_ each of them so
that we converge on a common set of rules that represent best practices
in software development.

It is natual, at the start of its life, for code to start as a
'rough and ready' implementation of a rapidly emerging design or concept.
During this 'pioneering' step initial implementations often avoid
introducing too many processes and tools as the trailblazing effort is
usually hampered and 'bogged-down', with efforts distracted by unnecessary rules.
In the early days too many 'quality' rules waste valuable development time
when your code is evolving rapidly where features appear and
disappear quickly. At this stage, development practices benefit from
being deliberately relaxed.

At some stage in the lifetime of the code it becomes _valuable_ and the desire
to control its behaviour becomes as important (or more important)
that enhancing it. It's at this stage, if you've left them out, you might be
thinking of code formatters, test frameworks, change-log, continuous integration,
and deployment and delivery options.

Rather than switch directly from the prototyping stage to a top-heavy
process that represents the 'ultimate' in assured quality in one step
the stages we describe here allow you to adopt the rules you need
onm a 'sliding scale' to allow gradual migration. And we have a lot of
repositories to consider.

The rules defined here are designed to promote consistency across diverse
repositories where developers may use employ different languages and tools.
The rules focus on a generic set of processes that should be compatible with
any software application. The rules help the observer and developer understand
how the software is documented, written, tested, built and delivered.

# Rules 1.0.0-alpha.1

**DOCUMENT UNDER REVIEW**

We have defined policies for four development stages, numbered 0 to 3.
The higher the stage number, the more demanding the policy.

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”,
“SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to
be interpreted as described in [RFC 2119].

## Stage 0
Repositories at **Stage 0** are the weakest in terms of policies. They
are repositories that represent new or legacy code that is yet to be promoted
to a higher stage. 

For agility the policy demands for **Stage 0** are deliberately weak.

1. The repository **SHOULD** have a README file in the root of the repository
2. The root README format **SHOULD** be one of Markdown (`.md`)
   or ReStructured Text (`.rst`)
3. The repository **SHOULD** display our "Policy Stage 0" badge in the README

>   **Stage Summary**: In order to understand how to contribute to or use a
    "Stage 0" repository you are likely to need to talk to the author.
    Process is weak, inconsistent and the build, test and delivery may be unclear

Use the badge in your project's README.md:
```md
[![Policy Stage: 0](https://img.shields.io/badge/policy%20stage-%280%29%20&#9734;&#9734;&#9734;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-stages)
```

Use the badge in your project's README.rst:
```doctest
.. image:: https://img.shields.io/badge/policy%20stage-%280%29%20&#9734;&#9734;&#9734;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-stages

```

Which looks like this:
![Policy Stage: 0](https://img.shields.io/badge/policy%20stage-%280%29%20&#9734;&#9734;&#9734;-dc332e)

> Repositories that have no badge SHOULD be considered "Stage 0" repositories.

## Stage 1
1. The repository **MUST** adopt our [Conventional Commit] message policy
2. Automated validation of the commit message **MUST** be implemented.
   This will normally be achieved using git's pre-commit hooks, which can be
   automatically configured using [pre-commit] and its corresponding
   `.pre-commit-config.yaml` file
3. The repository **MUST** have a README file in the root of the repository
4. The repository **MUST** clearly identify the repository build artefacts,
   i.e. what gets built (i.e. a container image). Users **MUST** expect
   to find a **Building** section in the README that contains instructions for
   building and publishing the artefacts
5  The repository **MUST** display our "Policy Stage: 1" badge in the README

>   **Stage Summary**: Commit messages conform to a standard, are enforced
    automatically, and it will be clear what the repository's artefacts are
    and how to build them and find them

Use the badge in your project's README.md:
```md
[![Policy Stage: 1](https://img.shields.io/badge/policy%20stage-%281%29%20&#9733;&#9734;&#9734;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-stages)
```

Use the badge in README.rst:
```doctest
.. image:: https://img.shields.io/badge/policy%20stage-%281%29%20&#9733;&#9734;&#9734;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-stages

```

Which looks like this:
![Policy Stage: 1](https://img.shields.io/badge/policy%20stage-%281%29%20&#9733;&#9734;&#9734;-dc332e)

## Stage 2
- The repository **MUST** satisfy all the policies defined in "Stage 1"
- The repository **MUST** employ CI/CD to build and publish the repo's artefacts
  For GitHub this will be the use of _Actions_ located in the repository's
  `.github/workflows` directory. For GitLab this will be the use
  of a `github-ci.yml` script
- The repository **MUST** document a branch policy
- Software releases **MUST** be identified using a release (GitHub) or
  a tag (GitLab or GitHub)
- Release numbers **MUST** us semantic versioning, and we typically support
  3-digit (`1.0.0`) and 2-digit (`2022.1`) styles, including pre-release
  conventions that introduce suffixes like `-rc.1`
- The repository **SHOULD** declare a code style guide
- The repository **SHOULD** contain and automatically run [Unit tests]

>   **Stage Summary**: Commit messages conform to a standard, are enforced
    automatically, repository artefacts are built automatically and
    development contributions using branches and release mechanisms
    will be clear

Use the badge in your project's README.md:
```md
[![Policy Stage: 2](https://img.shields.io/badge/policy%20stage-%282%29%20&#9733;&#9733;&#9734;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-stages)
```

Use the badge in your project's README.rst:
```doctest
.. image:: https://img.shields.io/badge/policy%20stage-%282%29%20&#9733;&#9733;&#9734;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-stages

```

Which looks like this:
![Policy Stage: 2](https://img.shields.io/badge/policy%20stage-%282%29%20&#9733;&#9733;&#9734;-dc332e)

## Stage 3
- The repository **MUST** satisfy all the policies defined in "Stage 3"
- The repository **MUST** declare a code style guide
- The repository **SHOULD** enforce the code style guide
- The repository **MUST** automatically run linting tools that are recognised
  by the community for the significant languages present in the repository.
  For example, if a repository contains Java and YAML, the observer can expect 
  to find linters for these language files.
- The repository **SHOULD** publish test coverage statistics
- The repository **MUST** contain clear instruction on how to use the artefacts
  i.e. it must have a guide for deploying and using the artefacts
- The repository **MUST** contain a CHANGELOG that is constructed automatically
  from the content of commit messages. If you use [Commitizen] as a tool
  to generate the CHANGELOG our [.cz.yaml] configuration file will be of value -
  it recognizes the commit message types and structures the CHANGELOG sections
  accordingly
- The CHANGELOG content **MUST** contain details of every commit, regardless of
  whether the change alters the code's behaviour. For example, documentation
  and test changes must be present in the CHANGELOG file.
- The repository **SHOULD** contain and automatically run [Functional tests]

>   **Summary**: A  strict set of policy rules. Commit messages and code style
    conform to a standard, and are enforced automatically. Code is built
    and can be deployed automatically. Users will clearly understand what is built,
    how it's built, how it's delivered, and what changes have been made

Use the badge in your project's README.md:
```md
[![Policy Stage: 3](https://img.shields.io/badge/policy%20stage-%283%29%20&#9733;&#9733;&#9733;-dc332e)](https://github.com/InformaticsMatters/code-repository-development-stages)
```

Use the badge in your project's README.rst:
```doctest
.. image:: https://img.shields.io/badge/policy%20stage-%283%29%20&#9733;&#9733;&#9733;-dc332e
    :target: https://github.com/InformaticsMatters/code-repository-development-stages

```

Which looks like this:
![Policy Stage: 3](https://img.shields.io/badge/policy%20stage-%283%29%20&#9733;&#9733;&#9733;-dc332e)

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
