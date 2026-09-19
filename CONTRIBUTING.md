# Contributing

Thank you for helping improve this skill.

## Principles

- Keep the workflow usable without creator-specific names, accounts, paths, portraits, or private reference images.
- Preserve the exact-title and identity-safety constraints.
- Use only examples and assets you are authorized to publish.
- Do not add claims about guaranteed reach, engagement, or virality.
- Keep `README.md` and `README.zh-CN.md` semantically equivalent.

## Before opening a change

```shell
rg -n 'file://|BEGIN (RSA |EC |OPENSSH )?PRIVATE KEY' .
git diff --check
```

Review every new binary asset manually. Portraits, generated user covers, and third-party screenshots should not be committed by default.
