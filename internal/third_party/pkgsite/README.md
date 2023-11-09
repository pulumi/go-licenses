# go/pkgsite/source

Vendored from <https://go.googlesource.com/pkgsite/+/8d5d35d6a95412a4720d586912c1a15f7da019f9/internal/source>,
because the source package is internal, and there's no plan to move it out anytime soon: <https://github.com/golang/go/issues/40477#issuecomment-868532845>.

The entire source folder and be downloaded via:

```bash
curl -LO https://go.googlesource.com/pkgsite/+archive/8d5d35d6a95412a4720d586912c1a15f7da019f9/internal.tar.gz
```

Local modifications:

- Update import paths.
- Removed unused functions from pkgsite/internal/stdlib, pkgsite/internal/derrors,
  pkgsite/internal/version to avoid other dependencies.
- For pkgsite/internal/source, switched to use go log package, because glog conflicts with a test
  dependency that also defines the "v" flag.
- Add a SetCommit method to type ModuleInfo in ./source/source_patch.go, more rationale explained in the method's comments.
