#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/orgs/Archiv8/fathom/discussions>
# Contributor: Ross Clark <https://github.com/orgs/Archiv8/fatho/discussionsm>


_langname="python"
_relname="fathom-web"

pkgname=(
  "${_langname}-${_relname}"
)
pkgver=3.7.1
pkgrel=1
pkgdesc="A supervised-learning system for recognizing parts of web pages—pop-ups, address forms, slideshows—or for classifying a page as a whole."
url="https://github.com/mozilla/fathom"
arch=(
  "any"
)
license=(
  "APACHE"
)
depends=(
  #  "nodejs"
  # Arch Linux Official Repositories
  "nodejs"
  "python-click"
  "python-filelock"
  "python-more-itertools"
  "python-numpy"
  "python-pytorch"
  "python-scikit-learn"

  # Archiv8 / AUR
  "python-tensorboardx"
  "python-selenium"

)
makedepends=(
  # Arch Linux Official Repositories
  "python-setuptools"
  # "jq"
  # "npm"
)
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_relname}-${pkgver}.tar.gz"
)
sha512sums=(
  "c66102fb38b379b6c23ce0178e7fb48376a5c9b9e7930adf34764481bc1fdba5733fcc49226c385b7534e564d063b618198c4f3ebdb488b54719d15ff0207b87"
)

build() {

  cd "$srcdir/${_relname}-$pkgver"

  python setup.py build
}

package() {

  cd "$srcdir/${_relname}-$pkgver"

  python setup.py install --root="$pkgdir/" --skip-build --optimize=1

  #  install -Dm644 "LICENSE.txt" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
