# Contributing
Instructions for making effective contributions to our projects.
* [License](LICENSE.md)
* [Changelog](CHANGELOG.md)
* [Contributing guide](README.md)

## Table of Contents
* [Our Vision](#vision)
* [Contributing](#contributing)
* [Development Environment](#dev-env)
* [Style Guide](#style)
* [Licensing](#licensing)
* [Examples](#examples)
* [Tags](#tags)

## Our Vision<a name="vision"></a>
*To drive the rapid growth of reliable autonomous aircraft with a focus on research and commercial applications with the highest potential to improve the environment, improve access to affordable mobility, and expand access to public services and goods. We will drive this rapid growth by developing flight systems with a focus on data quality, reliability, and robustness at a revolutionary price.*

## Contributing<a name="contributing"></a>
We welcome code contributions, bug reports, suggested enhancements, and assistance with documentation or testing. Use the repo's issue tracking system to identify potential bugs and suggested enhancements. Issue pull requests for making code contributions and assisting with documentation. If you have an idea to contribute and are unsure of the best approach, please contact us at support@bolderflight.com to discuss.

When issuing a bug report, be specific about:
   * The microprocessor used or Linux environment
   * Steps to reproduce the bug
   * Include code

## Development Environment<a name="dev-env"></a>
Be sure to check out our [Build Tools Guide](https://github.com/bolderflight/build-tools) for setting up your development environment.

## Style Guide<a name="style"></a>
Follow the [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html). Any parameter or variable names, which contain unit specific data should be appended with an underscore and the units (i.e. accel_z_mps2). For derived units, use _p_ to indicate _"per"_ and append exponents. So, m/s/s would be _mps2_ and kg/m^3 would be _kgpm3_. If a common abbreviation already exists for the unit, use that instead (i.e. _psi_ instead of _lbpin2_).

Prefer to use _float_ instead of _double_ unless there is a specific and demonstrated need for the additional resolution. Specify integer size in all cases where a certain number of bytes are expected (i.e. uint16_t where 2 bytes is assumed); otherwise use std::size_t or a signed int. Typically, we are not concerned with program size and int works well for integers and index values. If a certain number of bytes are needed they need to be called out directly since different compilers and platforms can change the number of bytes stored in a short, for instance. Do not assume that using unsigned int will prevent a negative input, instead use signed int and check for negative values.

Linting tests check for conformance to the style guide - analyzing the code for potential errors and leading to better readibility. [cpplint](https://raw.githubusercontent.com/google/styleguide/gh-pages/cpplint/cpplint.py) should be used to conduct linting tests with verbosity level 0. cpplint is installed in the development environment.

## Licensing<a name="licensing"></a>
If you use external sources, ensure they are licensed MIT, BSD, or a similarly permissive license. We would like to limit the amount of LGPL code and need to avoid GPL and unlicensed code.

If you would like to use external sources with licenses other than MIT or BSD, contact support@bolderflight.com to discuss options.

## Examples<a name="examples"></a>
Develop examples demonstrating your code's functionality and include expected outputs in comments. These examples provide an easy access point to learning your code and ensuring that it installed correctly.

## Tags<a name="tags"></a>
Tags are used to specify release version numbers in [semver](https://semver.org/) formatting. These tags are important because repositories using your code as a dependency will pull, build, and validate against a specific version, rather than continuously needing to manage code updates following HEAD.